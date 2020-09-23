<div align="center">

## Downloading HTTP with VB\.NET


</div>

### Description

Explains how to download http with VB.NET, includes a simple example.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Larry Bray](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/larry-bray.md)
**Level**          |Intermediate
**User Rating**    |4.0 (24 globes from 6 users)
**Compatibility**  |VB\.NET
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__10-9.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/larry-bray-downloading-http-with-vb-net__10-2861/archive/master.zip)





### Source Code

<br><br>
Downloading using HTTP with VB.NET is a fairly simple task. It really only takes four steps:<br><br>
1 - Use the <i>Create</i> method of the <i>System.Net.WebRequest</i> class to specify the web page. This method will return a <i>HttpWebRequest</i> if the web page is http://, it will return a <i>FileWebRequest</i> if the web page is file://.<br>
2 - Use the <i>GetResponse</i> method of the <i>WebRequest</i> object and return a <i>WebResponse</i> object for the web page.<br>
3 - Create a <i>StreamReader</i> or <i>BinaryReader</i> depending on the type of data to be downloaded.<br>
4 - The specifics that you need to perform on the stream.<br><br>
The following example simply displays the html of a web page -<br><br>
First, import <i>System.Net</i> and <i>System.IO</i> <br><br>
<pre>
Public Module Download
 Public Sub Main()
 Dim PgReq As HttpWebRequest = CType(WebRequest.Create(http://www.yahoo.com/index.html), HttpWebRequest)
 Dim PgResp As WebResponse = PageRequest.GetResponse()
 Dim sr As New StreamReader(PgResp.GetResponseStream())
 Dim Pg As String = sr.ReadToEnd()
 sr.Close()
 Console.Write(Pg)
 Console.ReadLine()
 End Sub
End Module
</pre>

