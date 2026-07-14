---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Test

## Test2

<div id="test-sortableTrash" class="sortable-code"></div> 
<div id="test-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="test-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="test-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
 var initial = `for (int i = 0; i < ablagestapel.length; i++)
{
    ablagestapel[i] = new ArrayStack<Karte>();
}
for (int i = 0; i < kaskaden.length; i++)
{
    kaskaden[i] = new ArrayStack<Karte>();
}`;
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "test-sortable",
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
  $("#test-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#test-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
