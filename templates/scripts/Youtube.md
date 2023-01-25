<%*
let url = await tp.system.clipboard();
let page = await tp.obsidian.request({url});
let p = new DOMParser();
let doc = p. parseFromString(page, "text/html");
let $ = s => doc.querySelector(s);

let qcFileName1 = $("meta[property='og:title']").content;
let qcFileName = qcFileName1.replace(/:/g, "_");
titleName = "🎬 " + qcFileName;
await tp.file.move("/Videos/"  + titleName);
let duration2 = $("meta[itemprop='duration']").content.slice(2);
let duration1 = duration2.replace(/M/gi, " Min ") ;
let duration = duration1.replace(/S/gi, " Sec ") ;
%>

---

tags: 🎬
aliases: 
  - 
cssclass: 
type: video

---

- `Title:` *<%
$("meta[property='og:title']").content %>
- `Type:` [[+]]
- `Tags:` 🎬 
- `URL:` <%
$("link[rel='shortLinkUrl']").href %>
- `Channel/Host:` <%
$("link[itemprop='name']").getAttribute("content") %>
- `Reference:` Details: <% $("meta[itemprop='description']").content %>
- `Publish Date:` <%
$("meta[itemprop='uploadDate']").content.slice(0, 4) %>
- `Duration`: <% duration %>
- `Status`: Not watched yet 
- `Reviewed Date:` [[<%tp.date.now()%>]]

---

# <% qcFileName %>

[<%
$("link[itemprop='name']").getAttribute("content") %>, ▶ *<%
$("meta[property='og:title']").content %>*, (<%
$("meta[itemprop='uploadDate']").content.slice(0, 4) %>)](<%
$("link[rel='shortLinkUrl']").href %>)


<center><iframe width="560" height="315" src="https://www.youtube.com/embed/<% $("meta[itemprop='videoId']").content %>" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

Details: <% $("meta[itemprop='description']").getAttribute("content") %>
