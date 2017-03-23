---
layout: post
title:  "Rails Polymorphic Associations"
date:   2017-03-23 01:45:26 +0000
---


I'm going to set the stage first with an example. You're creating a web application where users can create a review and they can also create a comment about one of those reviews. You'll create a review model and a comment model and the comment will belong to the review. If you wanted to add a way to like the review what would you do? 

Create a a like model with a review_id attribute? What about if you also wanted to create a like feature for your comments? We can't add a comment_id to the like model because then were going to have overlapping likes. How about we create a like model and then assign it a class based on the type of like it is. Review and Comment. Introducting Polymorphic Associations! 

Anytime you have something that can belong to more than one thing you can use Polymorphic. You would create your association like this.


rails g model Like likeable:references{polymorphic}
rake db:migrate

Your models would look like this:

class Review < ActiveRecord::Base
has_one :like, as: :likeable, depedent: :destroy
end

class Comment < ActiveRecord::Base
has_one :like, as: :likeable, depedent: :destroy
end

class Like < ActiveRecord::Base
  belongs_to :likeable, polymorphic: true
end


Here is how you would create a like in your console: 

review = Review.new
like = review.build_like
review.save

comment = Comment.new
like = comment.build_like
comment.save

Pretty cool! You can easily change your has_one association to has_many and then just access your likes instead of like. Polymorphic is a great way to organize your models and associations and makes it very easy to work with then one model can belong to multiple items. 

I hope this was helpful and you can use polymorphic associations in your future work! 

Happy coding. 






 

