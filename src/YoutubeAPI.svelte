<script>      //lang="Pls work :( :) uwu"
function start() {
  console.log(GAPIKEY);
  loadClient().then( () => {
    execute()
  });
 
  function getChannelId(username) {
    return gapi.client.youtube.channels.list({
      "part": [
        "id"
      ],
      "forUsername": username
    }).then( res => {
      return res.result.items[0].id;
    })
  }

  function loadClient() {
    gapi.client.setApiKey(GAPIKEY);
    return gapi.client.load("https://www.googleapis.com/discovery/v1/apis/youtube/v3/rest")
        .then(function() { console.log("GAPI client loaded for API"); },
              function(err) { console.error("Error loading GAPI client for API", err); });
  }

  function execute() {
    return gapi.client.youtube.playlists.list({
      "part": [
        "snippet"
      ],
      "channelId": getChannelId("ZimoNitrome")
    })
        .then(function(response) {
                // Handle the results here (response.result has the parsed body).
                console.log("Response", response);
              },
              function(err) { console.error("Execute error", err); });
  }


gapi.load('client', start);

</script>