  <template>
  <div>
    {{info}}
    </div>
  </template>

  <script type="text/javascript">
      const axios = require('axios');
      new Vue({
          data()  {
            return {
               info: null
            }
          },
          mounted() {
              axios
                  .get('https://jsonplaceholder.typicode.com/posts')
                  .then(function() {
                    response => (this.info = response);
                    console.log(this.info);
                  })
                  .catch(err=> {
                    alert(err);
                    console.log(err);
                  });
          },
      });
  </script>
