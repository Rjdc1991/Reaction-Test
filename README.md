# Reaction-Test

Hello World!

I have been studying front-end web development over the past year and have just discovered Github. I have designed a reaction test using HTML, CSS and Javascript. I am having an issue where some of the boxes will appear below the page, causing the scroll bar to appear, and having to scroll down to see the block. This being my first project, I expect it to be something minor. Thanks!

<html>
<head>
<title>Reaction Test!</title>
<h1>Test your reaction time!</h1>
<h2 id="showTime"></h2>

<style type = "text/css">
  #shape {

  height: 200px;
  width: 200px;
  background-color: red;
  display: none;
  position: relative;
  }

h1 {

  color: black;
  background-color: red;
  text-align: center;
  font-size: 60px;
  height: 80px;
  width: auto;
  font-family: Copperplate, "Copperplate Gothic Light", fantasy;
  -webkit-text-stroke: 1px white;

}

p {

  font-family: Copperplate, "Copperplate Gothic Light", fantasy;
  align: center;
  text-align: center;
  margin-right: 90px;

}

#button {

  margin-right:100px;
  margin-bottom:20px;
  background-color: red;
   border: none;
   color: white;
   padding: 15px 32px;
   text-align: center;
   text-decoration: none;
   display: inline-block;
   font-size: 16px;
}

body {
border: 5px solid red;
}

</style>
</head>
<body>
  
  <p> Click here to start! </p></br>

    <div style="text-align:center;">
      <button id="button">Go!</button>
    </div>

    <p> Your reaction time is: <span id="show"></span> </p>

  <div id="shape"></div>

<script type="text/javascript">

  var start = new Date().getTime();

  function appear() {

    var top = Math.random() * 400;

    var left = Math.random() * 400;

    var width = (Math.random() * 200) + 100;

                document.getElementById("shape").style.width = width + "px";

                document.getElementById("shape").style.height = width + "px";

                document.getElementById("shape").style.top = top + "px";

                document.getElementById("shape").style.left = left + "px";

                document.getElementById("shape").style.display = "block";

                start = new Date().getTime();


    }

    function delay() {

              setTimeout(appear, Math.random() * 2000);

          }

          document.getElementById("button").onclick = function () {

          delay();

          document.getElementById("shape").onclick = function() {

              document.getElementById("shape").style.display = "none";

              var end = new Date().getTime();

              var timeTaken = (end - start) / 1000;

              document.getElementById("show").innerHTML = timeTaken + " seconds";

              delay();

          }
        }

</script>
</body>
</html>

