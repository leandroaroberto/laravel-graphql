## Laravel GraphQL

This is a sample project to get more familiar with the usage of GraphQL hosted by a PHP client.

## Setup

After cloning this repo install laravel sail:

`php artisan sail:install`

Run the docker container with sail:

`vendor/bin/sail up -d`

Install all dependencies with composer:

`vendor/bin/sail composer install`

### GraphQL queries

TO run the queries open your favorite browser and go to <a href="http://localhost">http://localhost</a>

Show all quests

<pre>
{
    quests {
      id,
      title
    }
}
</pre>

Show quest where id is 1

<pre>
{
  quest(id: 1) {
    id,
    title,
    reward,
    description
  }
}
</pre>

Create a new Quest

<pre>
 mutation {
   createQuest(
     title: "Unbound"
     description: "Dragon has attacked heigen, RUN!!"
     reward: 20
     category_id: 1
   ){
     id
     title
     reward
     category{
       title
     }
     description
   }
 }
</pre>

Update a Quest where id is 11

<pre>
 mutation {
   updateQuest(
     id: 11,
     title: "Unbound 2"
     description: "Dragon has attacked white, RUN!!"
     reward: 200,
     category_id: 3
   ){
     id
     title
     reward
     category{
       title
     }
     description
   }
 } 
</pre>

Delete Quest where id is 11

<pre>
 mutation{
   deleteQuest(id: 11)
 }
 </pre>

## References

<a href="https://github.com/rebing/graphql-laravel">https://github.com/rebing/graphql-laravel</a>

<a href="https://www.freecodecamp.org/news/build-a-graphql-api-using-laravel/">https://www.freecodecamp.org/news/build-a-graphql-api-using-laravel</a>
