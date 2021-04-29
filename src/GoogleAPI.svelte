<script>
    import { GAPIKEY } from '.env';
    function start() {
      // 2. Initialize the JavaScript client library.
      gapi.client.init({
        'apiKey': {GAPIKEY},
      }).then(function() {
        // 3. Initialize and make the API request.
        return gapi.client.request({
          'path': 'https://people.googleapis.com/v1/people/me?requestMask.includeField=person.names',
        })
      }).then(function(response) {
        console.log(response.result);
      }, function(reason) {
        console.log('Error: ' + reason.result.error.message);
      });
    };
    // 1. Load the JavaScript client library.
    gapi.load('client', start);
    </script>

<svelte:head> 
    <!--Google core API-->
    <script src="https://apis.google.com/js/api.js"></script>

 
</svelte:head>


