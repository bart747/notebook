# Why Move UI-Related Stuff to a Server?

We've got a long history of wild changes
in the front-end/UI/close-to-UI area.
I mean the Web with browsers, Android, iOS,
desktop app interfaces, almost everything non-server-side.
Thy only stable and sane (to you) environment is a server
set up according to your liking.
When you wan to run your thing on many platforms,
only the server side of the system can be the same in each case.

You can limit this spread by doing more UI related work on a server
and sticking to simple layouts.
There's not much you can do when it comes to event listeners like
clicks, touches.
Rendering process is also case sensitive.
However, things like generating charts and graphs, image manipulation,
audio and video editing, packing data into readable formats,
whole HTML pages, can be done on a server.

Another aspect is unknown future.
What changes will force you to do extra work or mess up existing ideas?
You don't control app platforms.
You don't decide about browser or smartphone design.
The only place where you can pick and choose,
and than stick to it just because you like it, is the server-side
and your own computer.

2021-08-27
