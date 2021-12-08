<p> <b> IIS vs IIS Express vs Kestrel. </b></p>

If you want to know - why you need to use IIS with Kestrel in production mode, you will have to know the advantages of IIS Server over Kestrel.
Compared with Kestrel, IIS has many functions like logging, request tracking, reverse proxy and even server farm configurations. But it is not the fastest web server at present.

IIS Express is a lightweight IIS, integrated with Visual studio, designed for developers. IIS Express simulates IIS to the greatest extent, avoiding developers from publishing applications to IIS every time they test. At the same time, the lightweight feature of IIS Express allows developers to have a faster experience when testing.

In order to have a faster server, Microsoft created Kestrel. It uses a new request pipeline with ASP.NET Core. Things like HTTP modules & handlers have been replaced with simple middleware. The entire System.Web namespace is gone. Another big advantage is designing a web server to take advantage of async from the ground up. So far build the fastest ASP.NET application.

Although Kestrel can be used as a standalone web server, Microsoft does not recommend it. In the production environment, IIS acts as a reverse proxy server, sending requests to Kestrel and then entering the application. And before going on stage, developers can use the rich functions of IIS for troubleshooting during testing, which makes up for the shortcomings of Kestrel. Before the test environment, in the application development stage, using IIS Express and Kestrel is the most sensible choice.

![image](https://user-images.githubusercontent.com/5449746/145155402-035edeb6-28e0-445b-ad05-69446889bfcb.png)
