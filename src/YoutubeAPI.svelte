<script>
    
function start() {
  console.log(GAPIKEY);
console.log("uwu");
  // 2. Initialize the JavaScript client library.
  gapi.client.init({
    'apiKey': GAPIKEY,
  }).then(function() {
    // 3. Initialize and make the API request.
    return gapi.client.request({
      'path': 'https://www.googleapis.com/youtube/v3/playlists',
      'id': 'PLy3-VH7qrUZ5IVq_lISnoccVIYZCMvi-8'
    })
  }).then(function(response) {
    console.log(response.result);
  }, function(reason) {
    console.log('Error: ' + reason.result.error.message);
  });
};

gapi.load('client', start);

</script>