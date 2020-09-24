<div align="center">

## Get page from server when user presses the back or forward button


</div>

### Description

I searched high and low for a code which will allow me to get a fresh copy of my page even if the user presses the back or the ofrward button. Finally i gave up and wrote my own.

Expires and no-cache do not cache the page but it will still go into the history and can be retreived by the back button without going to the server

It needs IE5 or above to run
 
### More Info
 
Required IE5 or more


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Vikas Kumar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/vikas-kumar.md)
**Level**          |Advanced
**User Rating**    |5.0 (40 globes from 8 users)
**Compatibility**  |ASP \(Active Server Pages\), HTML, VbScript \(browser/client side\)

**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__4-9.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/vikas-kumar-get-page-from-server-when-user-presses-the-back-or-forward-button__4-6799/archive/master.zip)





### Source Code

```
cut the code below a save it as a asp.
when you run this code after pressing the back/forard button you will see it will automatically refresh
<%@ Language=VBScript %>
<%Response.Expires=0%>
<HTML>
<HEAD>
<META NAME="save" CONTENT="history">
<STYLE>
 .saveHistory {behavior:url(#default#saveHistory);}
</STYLE>
<SCRIPT>
var RandomValue;
 function fnSaveInput(){
  oPersistInput.setAttribute("sPersistValue",PersistedValue);
 }
 function fnLoadInput(){
  oPersistInput.value=oPersistInput.getAttribute("sPersistValue");
  RandomValue=oPersistInput.getAttribute("sPersistValue");
 }
 function f1()
 {
 if (RandomValue==PersistedValue)
	{window.location.reload(true)
	}
 }
</SCRIPT>
<%
Response.Write("<SCRIPT>")
Response.Write("var PersistedValue = '" & Now() & "';")
Response.Write("</SCRIPT>")
%>
</HEAD>
<BODY onload='f1()'>
<INPUT class=saveHistory onsave="fnSaveInput()" onload="fnLoadInput()" type=text id=oPersistInput>
</BODY>
<%
Response.Write(Now())
%>
</HTML>
```

