<iframe src="https://calendar.google.com/calendar/embed?height=600&amp;wkst=1&amp;bgcolor=%23FFFFFF&amp;src=6ga0b959sghi4furfh0mqt1qgc%40group.calendar.google.com&amp;color=%236B3304&amp;ctz=Asia%2FTokyo" style="border-width:0" width="800" height="600" frameborder="0" scrolling="no"></iframe>


<div id="gh-issues">
</div>


<script
  src="https://code.jquery.com/jquery-3.3.1.min.js"
  integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
  crossorigin="anonymous"></script>
  
<script>
var urlToGetAllOpenBugs = "https://api.github.com/repos/adamist521/karuizawa_keikaku/issues?state=open";

$(document).ready(function () {
    $.getJSON(urlToGetAllOpenBugs, function (allIssues) {
        $("#gh-issues").append("found " + allIssues.length + " issues</br>");
        $.each(allIssues, function (i, issue) {
            $("#gh-issues")
                .append("<b><a href=" + issue.html_url + " target='new' >" + issue.number + " - " + issue.title + "</a></b></br>")
                .append("created at: " + issue.created_at + "</br>")
                .append(issue.body + "</br></br></br>");
        });
    });
});
</script>
