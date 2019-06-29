<template>
  <div>
    {{info}}
    </div>  
</template>

<script>
    const axios = require('axios');
      export default {
          data: () => {
              return {
                  info: null,
              }
          },
          mounted() {
              axios
                  .get('https://jsonplaceholder.typicode.com/todos/1')
                  .then(function() {
                    response => (this.info = response);
                    console.log(this.info);
                  })
                  .catch(err=> {
                    alert(err);
                    console.log(err);
                  });
          },
      };
</script>       
