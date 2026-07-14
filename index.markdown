<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "for (int i = 0; i &lt; 52; i++) {
\n" +
    "    zahlen.add(i);
\n" +
    "} 
\n" +
    "//# TODO: Erzeugen Sie die Stacks für den Ablagestapel und die Kaskaden
\n" +
    "
\n" +
    "for (int i = 0; i &lt; ablagestapel.length; i++)
\n" +
    "{
\n" +
    "    ablagestapel[i] = new ArrayStack&lt;Karte&gt;();
\n" +
    "}
\n" +
    "for (int i = 0; i &lt; kaskaden.length; i++)
\n" +
    "{
\n" +
    "    kaskaden[i] = new ArrayStack&lt;Karte&gt;();
\n" +
    "}";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
