---
layout: page
type: lab-subpage
---

<table>
{% for c in page.source %}
<tr>
	<th>
		<a href="{{c}}">
		{{c}}
		</a>	
	</th>
</tr>
<tr>
	<th>

<div class="highlight">
<pre id="{{c}}" ></pre>
</div>
	</th>
	</tr>

{% endfor %}
</table>
<script type="text/javascript">

function ajax(url, box) {
var request =  new XMLHttpRequest();
request.open("GET", url, true);
request.setRequestHeader("Content-Type","application/x-www-form-urlencoded");

request.onreadystatechange = function() {
var done = 4, ok = 200;
if (request.readyState == done && request.status == ok) {
  if (request.responseText) {
	box.innerHTML = request.responseText;
        }
      }
    };
    request.send();
}

function getfiles() 
{
	{%for c in page.source%}
        var box =  document.getElementById("{{c}}");	
	if (box !== null)
	ajax("{{c}}", box);
	else
	alert("box found empty");
	{%endfor%}
(function() {
    var pre = document.getElementsByTagName('pre'),
        pl = pre.length;
    for (var i = 0; i < pl; i++) {
        pre[i].innerHTML = '<span class="line-number"></span>' + pre[i].innerHTML + '<span class="cl"></span>';
        var num = pre[i].innerHTML.split(/\n/).length;
        for (var j = 0; j < num; j++) {
            var line_num = pre[i].getElementsByTagName('span')[0];
            line_num.innerHTML += '<span>' + (j + 1) + '</span>';
        }
    }
})();
}

document.addEventListener('DOMContentLoaded', getfiles, false);
</script>