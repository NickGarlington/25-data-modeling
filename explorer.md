# Instructions

In each section below, you'll have some data described to you. List the models you would create, the fields those models would have, the data type for each field and a description of what the field is for. For example, if I said I wanted to model a todo, I might write something like:

## Todo Model
1. item - string - the actual description of what they want to do
2. completed - boolean - the status of whether it's completed or not
3. user_id - integer - the id for the user who owns this todo
4. created_at - datetime - when the todo was created

NOTE! For all of these, assume you have a User model that represents the person logged into the website.



# Quest 1 - Medium Clone

Let's start with an easy one. I've provided you with the minimum number of models, you just need to provide the field information. If you can think of additional normalized data that needs another model, don't feel restricted by what's here.

You're creating a simple Medium clone where people can write blog posts and comment on other people's blog posts. You want to have enough information to show the latest blog posts, blog posts for specific authors, and blog posts for specific categories. Categories and Authors need to match exactly for us to do this, so we'll make them their own models.

## Blog Post Model
  1. user_id - string - the name of the person posting.
  2. title - string - the subject of the post.
  3. created_at - datetime - when the blog was created.
  4. likes - integer - number of likes for this post.
  5. id - integer - unique identifier for this post.

## Comment Model
  1. comment_id - string - user responses for the post.
  2. quantity - integer - number of responses on the post.
  3. author_id - string - name of the person who is commenting.
  4. content - string - comments that the users make about the post.
  5. like - integer - how many likes there are for the comment.
## Author Model
  1. user_id - string - name of user.

## Category Model
  1. title - string - the name of the category.
  2. quantity - integer - the number of categories.



# Quest 2 - Twitter Clone

You're creating a Twitter clone. People can create tweets, follow other people and have followers. Keep in mind, unlike the blog post example where a comment is a separate entity, tweets responding to other tweets are still just tweets. Also, think about how Twitter turns a tweet into useful information. Do you think they scan tweets for @mentions and hashtags, or are they storing that kind of thing as additional fields? What models do we need to recreate Twitter?
## Tweet Model
   1. id - integer - unique identifier for the post.
   2. user_id - string - the name of the person posting.
   3. created_at - datetime - when the post was created.
   4. likes - integer - number of likes for this post.
   5. description - string - the subject matter of the post.
   6. media - string - video, image, or link inside the post.

## Image Model
   1. id - integer - the post where the image will be featured.
   2. image_id - integer - the number of images in the post.

## Hashtag Model
   1. name - string - name of the Hashtag.
   2. post_id - integer - the id of the post containing the hashtag.

## Retweet Model
   1. quantity - integer - the number of retweets in a post.
   2. post_id - integer - the id of the post being retweeted.
   3. user_id - string - the name of the person retweeting.
   4. description - string - the subject matter of the retweet.

## Categories Model
   1. title - string - name of the category.
   2. quantity - integer - the number of categories.

## Followers Model
   1. user_id - string - the name of the person following.
   2. others_id - string - the name of the person getting followed.

## Like Model
   1. quantity - integer - the number of likes for the post.
   2. post_id - integer - the id of the post.
   3. user_id - string - the name of the person liking the post.





# Quest 3 - Car Makes and Models

You're building a site that associates data with specific variations of specific cars. You need to break the data down from the manufacturer to the specific model. In other words, you need to model in such detail that the system knows that a 2007 Mustang and a 2013 Mustang are the _same_ thing (from the 5th Generation, 2005-2014), but that a 2015 Mustang is different from both of those. The car models should also know general information about the cars.
## Car Model
   1. id - integer - car vin number.
   2. name - string - name of the car.


## Manufacturer Model
   1. id - integer - unique identifier.
   2. name - string - name of manufacturer.
   3. car_id - integer - id of the car.



## Model Model
   1. id - integer - unique identifier
   2. name - string - the name of the model of the car.
   3. car_id - integer - car vin number.
   4. year - integer - year car was made.



## Generation Model
   1. model_id - integer - model of the car.
   2. name - integer - generation number


# Quest 4 - DC Comics

You've used the Marvel API quite a bit. Let's model a comic site of our own for DC. You'll need to think about the fact that there are characters (the superheroes), comics (the actual issues), series (the collections of issues), events (which consist of many issues), artists, writers, et cetera. This is an incredibly deep rabbit hole. Create at least 5 models that would be able to provide enough information for someone to build all of our Marvel apps, but in the DC universe.

## Character Model
   1. id - integer - unique identifier.
   2. name - string - name of character.
   3. comic_id - integer - id of all comics the character has appeared in.
   4. series_id - integer - id of all series the character has appeared in.
   5. events_id - integer - id of all the events the character appeared in.



## Comics Model
   1. id - integer - unique identifier.
   2. name - string - name of comics.
   3. issues - integer - issue number.
   5. series_id - integer - id of all series the character has appeared in.
   6. events_id - integer - id of all the events the character appeared in.


## Series Model
   1. events_id - integer - id of all series the character has appeared in.



## Events Model
   1. series_id - integer - id of all series the character has appeared in.
   2. character_id - integer - unique identifier.
   3. id - integer - unique identifier.



## Writers Model
   1. comics_id - integer - unique identifier.
   2. character_id - integer - unique identifier.
   3. series_id - integer - id of all series the character has appeared in.
   4. events_id - integer - id of all the events the character appeared in.


## Artists Model
   1. comics_id - integer - unique identifier.
   2. character_id - integer - unique identifier.
   3. series_id - integer - id of all series the character has appeared in.
   4. events_id - integer - id of all the events the character appeared in.
