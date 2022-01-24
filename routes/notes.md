to start server in terminal
    node server

<script>
    const http = require("http");

function aaa(callback) {
  // should be true for anything divisible by 3 between 0 and 9
  const bbb = Math.floor(Math.random() * 10) % 3 === 0;

  if (bbb) {
    callback(null, "YES");
  } else {
    callback(new Error("NO"));
  }
}

//create a server object:
http.createServer(function (req, res) {
    /* delete the line below and replace it with a call to aaa.
     write the callback function that is passed to aaa inline,
     within the parameter list in the function call */
    aaa((err, returnValues) => {
      if (err) {
        res.write(err.message);
      } else {
        res.write(returnValues);
      }
    });
    res.end(); //end the response
  })
  .listen(8080); //the server object listens on port 8080

// this is a fork of https://codesandbox.io/s/rl9v3156lp
</script>