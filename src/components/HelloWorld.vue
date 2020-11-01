

<script type = "text/javascript">
         var vm = new Vue({
            el: '#app',
            data: {
               name:'',
               currencyfrom : [
                  {name : "USD", desc:"US Dollar"},
                  {name:"EUR", desc:"Euro"},
                  {name:"INR", desc:"Indian Rupee"},
                  {name:"BHD", desc:"Bahraini Dinar"}
               ],
               convertfrom: "INR",
               convertto:"USD",
               amount :""
            },
            computed :{
               finalamount:function() {
                  var to = this.convertto;
                  var from = this.convertfrom;
                  var final;
                  switch(from) {
                     case "INR":
                     if (to == "USD") {
                        final = this.amount * 0.016;
                     }
                     if (to == "EUR") {
                        final = this.amount * 0.013;
                     }
                     if (to == "INR") {
                        final = this.amount;
                     }
                     if (to == "BHD") {
                        final = this.amount * 0.0059;
                     }
                     break;
                     case "USD":
                     if (to == "INR") {
                        final = this.amount * 63.88;
                     }
                     if (to == "EUR") {
                        final = this.amount * 0.84;
                     }
                     if (to == "USD") {
                        final = this.amount;
                     }
                     if (to == "BHD") {
                        final = this.amount * 0.38;
                     }
                     break;
                     case "EUR":
                     if (to == "INR") {
                        final = this.amount * 76.22;
                     }
                     if (to == "USD") {
                        final = this.amount * 1.19;
                     }
                     if (to == "EUR") {
                        final = this.amount;
                     }
                     if (to == "BHD") {
                        final = this.amount * 0.45;
                     }
                     break;
                     case "BHD":
                     if (to == "INR") {
                        final = this.amount *169.44;
                     }
                     if (to == "USD") {
                        final = this.amount * 2.65;
                     }
                     if (to == "EUR") {
                        final = this.amount * 2.22;
                     }
                     if (to == "BHD") {
                        final = this.amount;
                     }
                     break
                  }
                  return final;
               }
            }
         });
      </script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 
         #databinding{
            padding: 20px 15px 15px 15px;
            margin: 0 0 25px 0;
            width: auto;
            background-color: #e7e7e7;
         }
         span, option, input {
            font-size:25px;
         }
      
</style>
