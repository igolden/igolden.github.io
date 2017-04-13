Rails Counter Cache
===

I've been using counter_cache when I"ve refactored some older apps laterly, and found some intersting things.

Let's say I have simple User, Posts, and Comments associations: 

```
class User < ApplicationRecord
  has_many :posts
  has_many :comments, :through => :posts
end

class Post < ApplicationRecord
  belongs_to :user
end

class Comment < ApplicationRecord
  belongs_to :post
end
```

Simple enough. So let's look at a common use case for querying across all three models.

**Example**:
*On my "Publishers" page of my blog network, I want to display every publisher with a list of their last 10 blog posts. Here's the catch, I want them ordered by who has the most posts (most content) and by who has the most comments on their posts (most popular).*


So essentially, we need to be able to order our posts on: 

* Post.where(destination_id: params[:destination_id]).count
* Post.where(destination_id: params[:destination_id]).comments.count

Of course, we still need to get the Destination meta too.

* Destination.find(params[:id])

And combined

* Destination.includes(:posts, :comments).order(:posts_count)
* Destination.includes(:posts, :comments).order(:comments_count)

 
```
## BAD
users = User.all
users_with_assocation_data = []

users.each ||
  obj = {
    user: user,
    posts: user.posts,
    comments: user.comments
  }
  users_with_assocation_data << obj
end

return users_with_assocation_data
```

```

```





