---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Demo
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "print(&quot;Hello&quot;, endl=&quot;&quot;)\n" +
    "print(&quot; &quot;, endl=&quot;&quot;)\n" +
    "print(&quot;World!&quot;)\n" +
    "print(&quot;Hello&quot;) #distractor\n" +
    "print(&quot; &quot;) #distractor\n" +
    "print(&quot;World!&quot;, endl=&quot;&quot;) #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "sortableTrash"
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



