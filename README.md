See the page here: https://github.com/aflo7/wordpress_blog/deployments/github-pages

<hr>

Single post

- The following is code to show a single post on the page.
- For this application, I created an article element for each post.
- The posts are retrieved from an API, which is connected to a database.

```html
<article>
  <header>
    <span class="date">April 24, 2017</span>
    <h2>Sed magna ipsum faucibus</h2>
  </header>
  <a href="#" class="image fit">
    <img src="images/pic02.jpg" alt="" />
  </a>
  <p>
    Donec eget ex magna. Interdum et malesuada fames ac ante ipsum primis in
    faucibus. Pellentesque venenatis dolor imperdiet dolor mattis sagittis magna
    etiam.
  </p>
  <ul class="actions special">
    <li>
      <a href="#" class="button"> Full Story </a>
    </li>
  </ul>
</article>
```

<hr>

Random integer function

- The following function returns a random integer between two integers.
- I'm using the function to get a random number between 1-6, to select a random image for each blog post
- There are 6 images to choose from.
- I may eventually want to store the picture url as an attribute in the database, for each post.

```js
function randomIntFromInterval(min, max) {
  // min and max included
  return Math.floor(Math.random() * (max - min + 1) + min);
}
```

Fetch posts and display function

- This function calls the API and gets a list of all the posts currently inside Wordpress.
- Once the posts are retrieved, it renders each post to the page.
- Each post is rendered inside an article tag.
- The most important attributes we need from each post are it's title and content.

```js
async function fetchPostsAndDisplay() {
  const response = await fetch(
    'https://public-api.wordpress.com/wp/v2/sites/wpblog67.wordpress.com/posts'
  );
  const posts = await response.json(); // here is an array of objects, each object is a Post
  // continued
}
```
