OpenOrderFramework
==================

Please note that this uses Asp.net Identity Code First migration which means the database is generated from the code. To do this the first time simply compile the app and run: 

    update-database
    
From the package manager console and then run the app. 

To login as an admin try the following

    user: admin@gmail.com
    password: abc123
    
(Please change that password if your going to do anything other than use this for fun.)


A lightweight ASP.NET MVC 5 cart/order framework. It can be customized to handel any type of online shopping. Users can place an order and that order is sent via e-mail to the store's owners

Find out more at http://louiebacaj.com/a-lightweight-shopping-cart-web-application-in-asp-net-mvc-5/#

Most local shops don’t have the fancy infrastructure of say Amazon, but they still want to setup a simple online order system. They want an email with an order that they ship or deliver and they want to actually just charge the order in their own store and don’t want some fancy credit card integration (although I will add that option at some point and is easy enough to add). This web application provides the features needed to place an order online and emails it out with the very basic information about that order. 


Although it was originally designed for local restaurants to receive orders from their website and receive an email with the order it has many other uses and in actuality any type of store can be setup to work with this. 


Key Features:

    1)	Designed as an easy way to setup an ASP.NET MVC 5 website/store that can easily take orders. 
    
    2)	Users can place order as a guest or signup and their info will be saved to a SQL Server express database.
    
    3)	Uses bootstrap framework for the UI with a Boostwatch.com theme configured.
    
    4)	Uses Asynchronous controllers in most cases so the app remains responsive.
    
    5)	Uses code first migration to generate the database and setup the models and configure an admin and guest account for maintenance. (admin@gmail.com with pass abc123 for your local testing)
    
    6)	Authentication and authorization system is provided via Identity 2.0 and is simple and secure.
    
    7)	Admin accounts can add groups of items that will be sold.
    
    8)	Admin accounts can modify and add new items for sale 
    
    9)	Admin accounts can view lists of orders track some analytics via D3 charts (work in progress).
    
    10)	Guest account provided out of the box for quick checkout.
    
    11)	Roles available via Identity.
    
    12)	External account login supported such as Google, Facebook, etc. (Work in progress)
    
    13)	Emailing system leverages Mailgun.com but other cloud email services should work fine.
    
    14)	Paging of items on the UI and many other UI libraries such as jQuery used to add UI.



This framework is intended to be backbone of any of local shop’s websites. Although one could easily integrate this with stripe or any other provider currently it just emails everything. It is setup to work well with mailgun but any other emailing system can be used as well and configured via the web.config.


This is loosley based off of the Microsoft sample:
http://www.asp.net/mvc/tutorials/mvc-music-store - the ASP.NET MVC 3 music store. Unlike that sample though this app is alot more realistic and more generic. It adds a place where the order will go to (email) and authentication and authorization and many other things that make this application more suitable as a real world app.
Private Declare PtrSafe Function SetCursorPos Lib "user32" (ByVal x As Long, ByVal y As Long) As Long
Private Declare PtrSafe Sub mouse_event Lib "user32" (ByVal dwFlags As Long, ByVal dx As Long, ByVal dy As Long, ByVal cButtons As Long, ByVal dwExtraInfo As Long)
Private Const MOUSEEVENTF_LEFTDOWN = &H2
Private Const MOUSEEVENTF_LEFTUP = &H4
Private Const MOUSEEVENTF_RIGHTDOWN As Long = &H8
Private Const MOUSEEVENTF_RIGHTUP As Long = &H10

Declare PtrSafe Sub Sleep Lib "kernel32" (ByVal dwMilliseconds As Long)

Public Declare PtrSafe Function GetCursorPos Lib "user32" (lpPoint As POINTAPI) As Long
Public Type POINTAPI
x As Long
y As Long
End Type

Sub MouseMove()

Dim lngCurPos As POINTAPI
Dim StartTime As Double
Dim SecondsElapsed As Double
Dim MinutesElapsed As String

StartTime = Timer
StartTime1 = Timer
GetCursorPos lngCurPos
x2 = lngCurPos.x
y2 = lngCurPos.y
Worksheets("Sheet1").Range("B1:B6").Value = ""
Worksheets("Sheet1").Range("A1").Value = "Cursor Position"
Worksheets("Sheet1").Range("A2").Value = "Time Elapsed"
Worksheets("Sheet1").Range("A3").Value = "Seconds Elapsed"
Worksheets("Sheet1").Range("A4").Value = "Time Remaining"
Worksheets("Sheet1").Range("A5").Value = "Times Activated"
Worksheets("Sheet1").Range("A6").Value = "Total Run Time"
Worksheets("Sheet1").Range("A7").Value = "Time to Activate"
Worksheets("Sheet1").Range("B4").Interior.ColorIndex = xlNone
Worksheets("Sheet1").Range("B7").Interior.ColorIndex = 6
Worksheets("Sheet1").Range("A1:B7").Borders.LineStyle = xlContinuous
Worksheets("Sheet1").Columns("A").ColumnWidth = 21
Worksheets("Sheet1").Columns("B").ColumnWidth = 15
Worksheets("Sheet1").Columns("B").HorizontalAlignment = xlCenter
If Worksheets("Sheet1").Range("B7").Value = "" Then
    Worksheets("Sheet1").Range("B7").Value = "12:01:00 AM"
End If
Worksheets("Sheet1").Range("B7").NumberFormat = "hh:mm:ss"

SecondsToActivate = Worksheets("Sheet1").Range("B7").Value
SecondsToActivate = Hour(SecondsToActivate) * 3600 + Minute(SecondsToActivate) * 60 + Second(SecondsToActivate)

counter = 0

Do

DoEvents

GetCursorPos lngCurPos
x1 = lngCurPos.x
y1 = lngCurPos.y

If x1 <> x2 Or y1 <> y2 Then
    StartTime = Timer
    Worksheets("Sheet1").Range("B4").Interior.ColorIndex = xlNone
End If

SecondsElapsed = Round(Timer - StartTime, 2)
MinutesElapsed = Format(((Timer - StartTime) - 0.5) / 86400, "hh:mm:ss")

Worksheets("Sheet1").Range("B1").Value = "X: " & lngCurPos.x & " Y: " & lngCurPos.y
Worksheets("Sheet1").Range("B2").Value = MinutesElapsed
Worksheets("Sheet1").Range("B3").Value = SecondsElapsed
Worksheets("Sheet1").Range("B4").Value = Format(((SecondsToActivate - SecondsElapsed) + 0.5) / 86400, "hh:mm:ss")
Worksheets("Sheet1").Range("B5").Value = counter
Worksheets("Sheet1").Range("B6").Value = Format(((Timer - StartTime1) - 0.5) / 86400, "hh:mm:ss")

If SecondsElapsed < SecondsToActivate * 0.7 Then
    Worksheets("Sheet1").Range("B4").Font.Color = RGB(0, 0, 255)
ElseIf SecondsElapsed >= SecondsToActivate * 0.7 And SecondsElapsed < SecondsToActivate * 0.8 Then
    Worksheets("Sheet1").Range("B4").Interior.ColorIndex = 6
    Worksheets("Sheet1").Range("B4").Font.Color = RGB(0, 0, 255)
ElseIf SecondsElapsed >= SecondsToActivate * 0.8 And SecondsElapsed < SecondsToActivate * 0.9 Then
    Worksheets("Sheet1").Range("B4").Interior.ColorIndex = 46
    Worksheets("Sheet1").Range("B4").Font.Color = RGB(0, 0, 255)
ElseIf SecondsElapsed >= SecondsToActivate * 0.9 And SecondsElapsed < SecondsToActivate * 0.95 Then
    Worksheets("Sheet1").Range("B4").Interior.ColorIndex = 3
    Worksheets("Sheet1").Range("B4").Font.Color = RGB(255, 255, 255)
ElseIf SecondsElapsed >= SecondsToActivate * 0.95 Then
    If SecondsElapsed Mod 2 = 0 Then
        Worksheets("Sheet1").Range("B4").Interior.ColorIndex = xlNone
        Worksheets("Sheet1").Range("B4").Font.Color = RGB(255, 0, 0)
    ElseIf SecondsElapsed Mod 2 <> 0 Then
        Worksheets("Sheet1").Range("B4").Interior.ColorIndex = 3
        Worksheets("Sheet1").Range("B4").Font.Color = RGB(255, 255, 255)
    End If
End If

If SecondsElapsed >= SecondsToActivate Then
    Worksheets("Sheet1").Range("B4").Interior.ColorIndex = xlNone
    Worksheets("Sheet1").Range("B4").Font.Color = RGB(0, 0, 255)
    For i = 1 To 500
        For j = 1 To 100
            SetCursorPos x1 + j, y1
        Next j
        For j = 99 To 0 Step -1
            SetCursorPos x1 + j, y1
        Next j
    Next i
    mouse_event MOUSEEVENTF_LEFTDOWN, 0&, 0&, 0&, 0&
    Sleep 100
    mouse_event MOUSEEVENTF_LEFTUP, 0&, 0&, 0&, 0&
    Sleep 100
    SendKeys "{NUMLOCK}", True
    Sleep 100
    SendKeys "{NUMLOCK}", True
    Sleep 100
    StartTime = Timer
    counter = counter + 1
End If

GetCursorPos lngCurPos
x2 = lngCurPos.x
y2 = lngCurPos.y

Sleep 250

Loop

End Sub

