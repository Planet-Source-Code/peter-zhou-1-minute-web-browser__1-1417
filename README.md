﻿<div align="center">

## \<1 Minute Web Browser\!\!\!


</div>

### Description

You boss wants a webbrowser by 12, it's 11:59, just copy and paste this source and you'll get a cool looking black and white web browser in less than a minute!!!
 
### More Info
 
Just create a file called Webfrm.frm in notepad and copy and paste the code in it and then start a project in VB and add the frm file in!!!


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Peter Zhou](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/peter-zhou.md)
**Level**          |Unknown
**User Rating**    |2.5 (28 globes from 11 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Internet/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-html__1-34.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/peter-zhou-1-minute-web-browser__1-1417/archive/master.zip)





### Source Code

```
*** paste into webfrm.frm in notepad after this line ***
VERSION 5.00
Object = "{EAB22AC0-30C1-11CF-A7EB-0000C05BAE0B}#1.1#0"; "SHDOCVW.DLL"
Begin VB.Form Webfrm
  BackColor    =  &H00000000&
  BorderStyle   =  3 'Fixed Dialog
  Caption     =  "Web Browser"
  ClientHeight  =  5295
  ClientLeft   =  45
  ClientTop    =  330
  ClientWidth   =  7455
  BeginProperty Font
   Name      =  "Tahoma"
   Size      =  8.25
   Charset     =  0
   Weight     =  400
   Underline    =  0  'False
   Italic     =  0  'False
   Strikethrough  =  0  'False
  EndProperty
  LinkTopic    =  "Form1"
  MaxButton    =  0  'False
  MinButton    =  0  'False
  ScaleHeight   =  5295
  ScaleWidth   =  7455
  ShowInTaskbar  =  0  'False
  StartUpPosition =  3 'Windows Default
  Begin VB.ListBox lstFavs
   Height     =  255
   Left      =  3960
   TabIndex    =  11
   Top       =  480
   Visible     =  0  'False
   Width      =  1335
  End
  Begin VB.CommandButton cmdAdd
   BackColor    =  &H80000005&
   Caption     =  "Add to Favorites"
   Height     =  255
   Left      =  6000
   Style      =  1 'Graphical
   TabIndex    =  10
   Top       =  840
   Width      =  1335
  End
  Begin VB.CommandButton cmdFav
   BackColor    =  &H80000005&
   Caption     =  "Favorite"
   Height     =  255
   Left      =  4320
   Style      =  1 'Graphical
   TabIndex    =  9
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdSearch
   BackColor    =  &H80000005&
   Caption     =  "Search"
   Height     =  255
   Left      =  5160
   Style      =  1 'Graphical
   TabIndex    =  8
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdForward
   BackColor    =  &H80000005&
   Caption     =  "Forward"
   Height     =  255
   Left      =  960
   Style      =  1 'Graphical
   TabIndex    =  7
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdHome
   BackColor    =  &H80000005&
   Caption     =  "Home"
   Height     =  255
   Left      =  3480
   Style      =  1 'Graphical
   TabIndex    =  6
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdReload
   BackColor    =  &H80000005&
   Caption     =  "Reload"
   Height     =  255
   Left      =  2640
   Style      =  1 'Graphical
   TabIndex    =  5
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdStop
   BackColor    =  &H80000005&
   Caption     =  "Stop"
   Height     =  255
   Left      =  1800
   Style      =  1 'Graphical
   TabIndex    =  4
   Top       =  120
   Width      =  735
  End
  Begin VB.CommandButton cmdBack
   BackColor    =  &H80000005&
   Caption     =  "Back"
   Height     =  255
   Left      =  120
   Style      =  1 'Graphical
   TabIndex    =  3
   Top       =  120
   Width      =  735
  End
  Begin VB.ComboBox txtUrl
   Height     =  315
   Left      =  720
   Style      =  1 'Simple Combo
   TabIndex    =  2
   Text      =  "C:\"
   Top       =  840
   Width      =  5175
  End
  Begin SHDocVwCtl.WebBrowser WebBrowser1
   Height     =  3975
   Left      =  120
   TabIndex    =  0
   Top       =  1200
   Width      =  7215
   ExtentX     =  12726
   ExtentY     =  7011
   ViewMode    =  1
   Offline     =  0
   Silent     =  0
   RegisterAsBrowser=  0
   RegisterAsDropTarget=  1
   AutoArrange   =  -1 'True
   NoClientEdge  =  0  'False
   AlignLeft    =  0  'False
   ViewID     =  "{0057D0E0-3573-11CF-AE69-08002B2E1262}"
   Location    =  ""
  End
  Begin VB.Label Label1
   BackColor    =  &H00000000&
   Caption     =  "Go To:"
   ForeColor    =  &H80000005&
   Height     =  255
   Left      =  120
   TabIndex    =  1
   Top       =  840
   Width      =  615
  End
End
Attribute VB_Name = "Webfrm"
Attribute VB_GlobalNameSpace = False
Attribute VB_Creatable = False
Attribute VB_PredeclaredId = True
Attribute VB_Exposed = False
Dim FN As Integer
Private Sub cmdAdd_Click()
FN = FreeFile
Open "c:\favs.txt" For Output As FN
Print #FN, txtUrl.Text & Chr(13)
Close #FN
End Sub
Private Sub cmdBack_Click()
On Error Resume Next
WebBrowser1.GoBack
End Sub
Private Sub cmdFav_Click()
On Error Resume Next
FN = FreeFile
Open "c:\favs.txt" For Input As FN
lstFavs.Visible = True
Do Until EOF(FN)
Line Input #FN, NextLine$
lstFavs.AddItem NextLine$
Loop
Close #FN
End Sub
Private Sub cmdForward_Click()
On Error Resume Next
WebBrowser1.GoForward
End Sub
Private Sub cmdHome_Click()
WebBrowser1.GoHome
End Sub
Private Sub cmdReload_Click()
WebBrowser1.Refresh
End Sub
Private Sub cmdSearch_Click()
WebBrowser1.GoSearch
End Sub
Private Sub cmdStop_Click()
WebBrowser1.Stop
End Sub
Private Sub Form_Load()
URL$ = "c:\"
WebBrowser1.Navigate URL$
End Sub
Private Sub lstFavs_Click()
txtUrl.Text = lstFavs.List(lstFavs.ListIndex)
txtUrl_KeyPress 13
lstFavs.Visible = False
Close #FN
End Sub
Private Sub txtUrl_KeyPress(KeyAscii As Integer)
On Error Resume Next
If KeyAscii = 13 Then
URL$ = txtUrl.Text
WebBrowser1.Navigate URL$
End If
End Sub
```

