// Fetch data from an API using promise chaining
fetch('https://api.example.com/users')
  .then(response => response.json())
  .then(users => {
    // Process the user data and fetch additional data for each user
    const userIds = users.map(user => user.id);
    return fetch(`https://api.example.com/posts?users=${userIds.join(',')}`);
  })
  .then(response => response.json())
  .then(posts => {
    // Process the post data and fetch additional data for each post
    const postIds = posts.map(post => post.id);
    return fetch(`https://api.example.com/comments?posts=${postIds.join(',')}`);
  })
  .then(response => response.json())
  .then(comments => {
    // Process the comment data
    console.log('Comments:', comments);
  })
  .catch(error => {
    // Handle errors from any of the promises
    console.error('Error:', error);
  });
