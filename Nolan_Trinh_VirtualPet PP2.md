<!DOCTYPE html>
<html>

<!--
  Author: Nolan
  Class COMP105
  Project: Virtual Pet Enhancement
  Helpers: Revaz, Katie, Marrisa, Aleksander, Dr,Alyce.
-->

<head>
<title>Virtual Pet</title>

<script type="text/javascript">

    function showTime()
    {
        document.getElementById('timeP').innerHTML = Date();
    }
    setInterval("showTime()", 1000);


    function initialize()
    {
        counter.value= 0;
        state.value = "Calm";
        setInterval("updatestate()", 1000); //This would call a function evey 1000 millisec
        updatestate();
    }
  /**
    function initialize()
    {
        counter.value= 0;
        state.value = "Calm";
        setInterval("updatestate()", 1000); //This would call a function evey 1000 millisec
        doIt();
    }
    
    function updatestate() //This would change the value of the number added to the counter textbox
    {
      counter.value ++;
      //if function to be added , based on probability and current state.
      //now update action and sound to match new state
      //var randomVal = Math.random();
      doIt();
    }
*/
    function updatestate() //This would change the value of the number added to the counter textbox
    {
      //if function to be added , based on probability and current state.
      //now update action and sound to match new state
      //var randomVal = Math.random();
      if(paused == false)
      counter.value ++;
      doIt();
      var randomVal2 = Math.random();
      if( state.value == "Happy" && randomVal2 < 0.4 )
        state.value = "Angry";
    }


    //This function will display the action and sound tht match the current state
    function doIt ()
    {
      if ( state.value == "Happy" )
      {
	   petAction.value = "Woof woof";
     document.getElementById('picture').src = "download1.jpg";
      }
      else if ( state.value == "Angry" )
      {
	   petAction.value = "Snarl";
     document.getElementById('picture').src = "download2.jpeg";
      }
      else if ( state.value == "Depressed" )
      {
	   petAction.value = "Snoring";  
     document.getElementById('picture').src = "download0.jpeg";
      }
      else if ( state.value == "Calm" )
      {
	   petAction.value = "Napping";  
     document.getElementById('picture').src = "download3.jpeg";
      }
      else if( state.value == "Silent")
      {
    petAction.value = "Flexxing out";
    document.getElementById('picture').src = "download4.jpeg";
      }
      else{   // state.value is neither hungry nor asleep
	  petAction.value = "Quiet";
    document.getElementById('picture').src = "download5.jpeg";
      }
    }

    function Pat()
    {
      var randomVal = Math.random();
      if ( state.value == "Calm" && randomVal < 0.4)
      {
        state.value = "Happy";
        doIt();
      }
      else if ( state.value == "Calm" && randomVal > 0.4)
      {
        state.value = "Provoked";
        doIt();
      }
      else if ( state.value == "Happy" && randomVal < 0.2)
      {
        state.value = "Provoked";
        doIt();
      }
      else if ( state.value == "Happy" && randomVal > 0.2)
      {
        state.value = "Calm";
        doIt();
      }
      else if ( state.value == "Angry" )
      {
        state.value = "Calm";
        doIt();
      }  
    }

    function Ignore()
    {
      var randomVal1 = Math.random();
      if ( state.value == "Happy")
      {
        state.value = "Depressed";
        doIt();
      }
      else if ( state.value == "Depressed"  && randomVal1 < 0.2 )
      {
        state.value = "Provoked";
        doIt();
      }
      else if ( state.value == "Depressed" && randomVal1 > 0.2)
      {
        state.value = "Angry";
        doIt();
      }
      else if ( state.value == "Provoked" && randomVal1 > 0.3)
      {
        state.value = "Silent";
        doIt();
      }
      else if ( state.value == "Provoked" && randomVal1 < 0.3)
      {
        state.value = "Angry";
        doIt();
      }
    }

var paused = false;

function pause()
{
  if( paused == false)
  {
    paused = true;
    pat.disabled = true;
    ignore.disabled = true;
    muter.value = "Resume";
    updatestate.disabled = true;
    initialize.disabled = true;
    counter.disabled = true;
  }
  else if( paused == true)
  {
    paused = false;
    pat.disabled = false;
    ignore.disabled = false;
    muter.value = "Pause";
    updatestate.disabled = false;
    initialize.disabled = false;
    counter.disabled = false;
  }
}


function visibility()
  {
    if(counter.style.visibility == "visible")
    {
    counter.style.visibility = "hidden";
    state.style.visibility = "hidden";
    petAction.style.visibility = "hidden";
    petSound.style.visibility = "hidden";
    }
    else
    {
    counter.style.visibility = "visible";
    state.style.visibility = "visible";
    petAction.style.visibility = "visible";
    petSound.style.visibility = "visible";
    }
  }

</script>
</head>

<body onload="initialize()"> <!--the initialize() is the function Initilization name that will be given-->
<!--the tag onload will immediately execute the function stated in the dub bracket to appear on the webpage-->
        <br>
        <h1>Date and Time is:</h1>
        <p id="timeP">
        &nbsp;
        </p>


        <H2>
        <FONT style="color:#009966;">Tralfaz, the Wonder Dog</FONT>
        </H2>
        <center><div class="center"><img id="picture" src="download0.jpeg"  height=125 align=middle> </div></center>


        <center><P>
          <label for="petAction">Pet Movement: </label>
            <input TYPE=text ID=petAction SIZE=35>
        </p></center>
            
        <center><P>
          <label for="petSound">Pet Sound </label>
          <input TYPE=text ID=petSound SIZE=35>
      </p></center>

        <center><P>
          <label for="counter">Counter: </label>
          <input TYPE=text ID=counter  SIZE=35> <!-- This would add a box for addinng a counter for the seconds the pet will chnge states-->
        </p>
        <label for="state">State: </label>
          <input TYPE=text ID=state SIZE=35>  <!-- This would add a box for addinng a counter for the seconds the pet will chnge states-->
        </p></center>



        <center><P> 
            <input type=button id="pat" value="Pat the dog" onclick = "Pat()" >
            <input type=button id="ignore" value="Ignore the dog" onclick="Ignore()">
        </p></center>



        
        <input type="button" name="Pause" id="muter" value="Pause" onclick="pause()" ><label for="muter">Pause/Resume</label></div>
        
        <input type="button" name="Visible" id="visible" value="Visible" onclick="visibility()" ><label for="visible">Visibility</label></div>
</body>

</html>