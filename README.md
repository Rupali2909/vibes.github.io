<!DOCTYPE html>
<html>
    <style>
       
        body
        {
           background-image: url("https://upload.wikimedia.org/wikipedia/commons/6/6c/NIT_Durgapur_front_.jpg");
           width: 100%;
           height: 2000px;
           background-size: cover;
           background-position:center;
           background-repeat: no-repeat;
           position:relative;
        }
        .Division
        {
            
            border-radius: 50px;
            background-color: aliceblue;
            opacity: 65%;
            padding-top: 50px;
            position: relative;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            width: 500px;
            max-width: 50%;
            height: 700px;
            max-height: 50%;
        }
        h1
        {
            text-align: center;
            font-family: cursive;
            font-size: 50px;
            color: black;
            position: relative;
        }
        p
        {
            text-align: center;
            font-size: 25px;
            font-family: cursive;
            color: black;
            position: relative;
        }
        
    </style>
    <body>
	<p>Current Date and Time is <span id='date-time'></span>.</p>
        <div class = "Division">
            <h1> Data </h1>
            <br>
            <p id = "Updated" class = "Updated">Updated : </p>
            <br>
            
            <p id = "rate" class = "rate">rate : </p>
            <br>
            <br>
        </div>
        <script>
            const urlrate = 'https://io.adafruit.com/api/v2/Rupali29/feeds/labdata';
            async function getISS()
            {
                
               const response = await fetch(urlrate);
               const data = await response.json();
               console.log(data);
		console.log(data.last_value);
               console.log(data.updated_at, data.last_value);
               var up = document.getElementById("Updated");
               up.textContent = "Updated : " + data.updated_at;
               
               var rate = document.getElementById("rate");
               rate.textContent = "rate : " + data.last_value;
            }
            getISS();
        </script>
      <meta http-equiv="refresh" content="5;" />
    </body>
</html>
