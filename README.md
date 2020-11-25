# bookstore405web
a simple Grails 4.0.5 web application created via the Grails Application Forge web site

Previously I used my MS Windows 10 Pro laptop (a Dell XPS 15) to visit the Grails Application Forge web site (http://start.grails.org/) and generated 
two Grails 4.0.5 web applicationa -- one for the "web" profile and one for the "angular" profile.

```
11/14/2020  02:16 PM           807,978 bookstore405web.zip
11/14/2020  02:17 PM           264,485 bookstore405ng.zip
```

This github repository reflects my work with the "web" profile "bookstore405web" Grails 4.0.5 web application.

Here are the files I downloaded in order to work on this project:

```
07/16/2020  09:10 AM       174,353,032 jdk-8u261-windows-x64.exe
10/24/2020  09:13 AM       159,488,664 jdk-11.0.9_windows-x64_bin.exe
10/24/2020  09:14 AM       179,769,466 jdk-11.0.9_windows-x64_bin.zip
10/26/2020  06:14 AM       134,272,314 grails-4.0.5.zip
10/26/2020  06:14 AM         9,113,697 grails-docs-4.0.5.zip
11/14/2020  01:50 PM       697,317,424 ideaIU-2020.2.3.exe
11/14/2020  01:52 PM       806,810,701 ideaIU-2020.2.3.win.zip
11/14/2020  01:52 PM       601,519,616 ideaIC-2020.2.3.exe
11/14/2020  01:53 PM       675,182,337 ideaIC-2020.2.3.win.zip
```

Afer installing the two versions of the Oracle Java JDK (8u261 and 11.0.9), Grails 4.0.5, and the JetBrains IntelliJ IDEA, I used the command line to build 
the simple "bookstore405web" web application and test it with the Firefox web browser (at URL http://localhost:8080).  For this initial work I used the Java 8u261 JDK.

```
Microsoft Windows [Version 10.0.19042.630]
(c) 2020 Microsoft Corporation. All rights reserved.

C:\Users\David Holberton>grails --version
| Grails Version: 4.0.5
| JVM Version: 1.8.0_261
C:\Users\David Holberton>java -version
java version "1.8.0_261"
Java(TM) SE Runtime Environment (build 1.8.0_261-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.261-b12, mixed mode)

C:\Users\David Holberton>
```

Here is the command line activity for the initial build of the "bookstore405web" Grails 4.0.5 web application:

```
cd "\Users\David Holberton"
mkdir g2mprojects
cd Downloads
copy bookstore405web.zip ..\g2mprojects
cd ..\g2mprojects
7z l bookstore405web.zip > ..\bookstore405web.zip.txt
7z x bookstore405web.zip
cd bookstore405web
tree /a    > ..\..\bookstore405web-tree-a.txt
tree /a /f > ..\..\bookstore405web-tree-af.txt
git init
git add .
git commit -a -m "initial commit"
git remote add origin https://github.com/ashburndev/bookstore405web.git
git branch -M main
git push -u origin main
grails run-app

grails create-domain-class Book
notepad grails-app\domain\bookstore405web\Book.groovy
grails generate-all bookstore405web.Book
grails schema-export
copy .\build\ddl.sql ..\..\bookstore405web.ddl.sql
grails run-app
```
