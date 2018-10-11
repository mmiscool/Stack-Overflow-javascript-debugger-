# Stack-Overflow-javascript-debugger-
Add a stack overflow javascript debugger to your project. This will allow javascript errors to be automagicaly caught and searched on stack overflow 

Add the below snipet to any html file and the debugger will be there. 

Have fun



```

<div id="debuggerDiv" style="display:none">
  <select id="StackOverflowDebuggerList" size="10" onDblClick="//alert(this.value);
  window.open( 'https://stackoverflow.com/search?q=[js]+' + this.value, '_blank');">
  </select>
</div>

<div style="position: fixed;top: 1px;left: 50%;">
  <button onclick="toggleStackOverflowDebugger();">Show debugger</button>
</div>


<script type="text/javascript">
showCrazyFunDebugger = false;
window.onerror = function(msg, url, line, col, error) {
   var extra = !col ? '' : '\ncolumn: ' + col;
   extra += !error ? '' : '\nerror: ' + error;
   //alert("Error: " + msg + "\nurl: " + url + "\nline: " + line + extra);
  // $("#debuggerList").append(new Option( error,  error));

   StackOverflowDebuggerList = document.getElementById("StackOverflowDebuggerList")
   StackOverflowDebuggerList.options[StackOverflowDebuggerList.options.length] = new Option(error,  error);


   var suppressErrorAlert = true;
   return suppressErrorAlert;
};

function toggleStackOverflowDebugger(){
  if(showCrazyFunDebugger != undefined && showCrazyFunDebugger != true){
    showCrazyFunDebugger = true;
  }
  else{
    showCrazyFunDebugger = false;
  }
  if (showCrazyFunDebugger == true){
    document.getElementById('debuggerDiv').style = 'position: fixed;top: 10%;left: 10%;';
  }else{
    document.getElementById('debuggerDiv').style = 'display:none';
  }
}
</script>


``
