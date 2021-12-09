# A Quick Tour Of The Web

## Learning Goals

- Define "internet"
- Define "server" role
- Define "client" role
- Identify which role possesses the data that browsers display
- Identify what type of content defines what's seen in browsers

## Introduction

Welcome to the web, the largest canvas in the world. Over half of the world's
population has access to the web. Never before has it been possible to reach so
many across such vast distances!

![Welcome to the Web!](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_10A.png)

To orient you in these first steps of your study of HTML and web programming we
want to give a broad overview of the web and how it works in the broadest terms.
While you might have heard "web," and "internet" and "server" in many different
contexts and places over the years, it's possible that you've never built a
cohesive model in your mind that connects those concepts.

In this lesson, we'll go over the essential steps in how the web works.

## Define "internet"

When people share information, great things can happen. Politics can change. Our
place in the universe can change. Disease can be conquered. The ability to share
knowledge is _power_. In the earliest days of computing, engineers looked for
ways to have computers share information. Technical limits meant networked
computers had to be within the same office.

Eventually, improvements allowed small networks to "inter"-"network" with each
other. This discipline was called "internetworking." By the technology and
knowledge of "internetworking," these small local networks (or, "local area
networks" or LANs) became "internetworked" into "Wide Area Networks" or WANs.

![Visual Internet](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_18_VisualInternet.png)

The natural next dream was to "internetwork" WANs into some sort of "larger"
inter-network, something city-scale, country-scale, or global scale. Technology
for "inter-networking" WANs was difficult and slow to develop, but eventually
produced a backbone internetwork, "**The Internet**work" which encompassed all
of its constituent WANs and their constituent LANs. Eventually, in common usage,
it became called "The Internet."

![The internet](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_10B.png)

It was upon _this_ "The Internet" that "The Web" was built.

**Note:** For many reasons, style guides no longer capitalize "internet" or
"web." The global network linking computers globally is "the internet."

## Define "server" Role

All machines on the internet are computers. For ease of discussion, we're going
to discuss them in two "roles:" client and server. Historically a "server" would
be a larger, more powerful computer with more memory, bigger hard drives, and
more computer chips. But today, "server" roles can be handled quite well by
Arduino devices no bigger than a credit card! Nevertheless, in diagrams and on
whiteboards they tend to be drawn as large "tower-style" computers.

Regardless of its size, a "server" has the responsibility of arranging the data
that is presented to the "client." It's because of this "arranging" being
computationally demanding that servers have tended to have extra resources.

Historically, computers were very expensive and well-appointed servers were
very, very expensive. As such, when possible, it was more economical for servers
to do heavy processing and for the clients to request updates.

## Define "client" Role

A computer fulfilling a client role has the responsibility of presenting the
data that is sent from the server. Historically, these machines could be more
lightly equipped (and thus cheaper). You'll generally see them drawn in diagrams
or on whiteboards as laptops.

The _client_ displays data that is provided to it by the _server_. A verb that's
commonly used is "render" as in, "The client _renders_ data provided by the
server." That is, it only displays the server's data and any change to the data
has to be done _by the server_, caused by a _request_ from the _client_.

![Client/Server Role](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_19_BasicClientServer.png)

## Client/Server Example

Let's take a moment to consider client/server in a common scenario: the
supermarket.

If you ask the cashier for the price of a bottle of water, they can look it up
for you. But their client computer's "source of truth" on the price lives on the
server. The _client_ must request this information by "asking" or "sending a
request" to the _server_.

Similarly, when you buy that bottle of water, the (lightweight) client says
"Sold a bottle of water!" to a server. The server, in turn, updates its
inventory record to show `-1` water bottle.

Now, at the end of the sales day, the management team would like to do some
analytics about how profitable they were that day. They _could_ go to each
client computer, determine its revenue for the day and which departments
contributed to that number, but on a cheap client machine that process would be
s..l...o.....w — like trying to play a PS5 game on an iPhone!

_However_, if each client computer merely logged its actions to the server by
sending requests, the management could ask that high-power machine to print out
analytics in an economical and efficient fashion. Many businesses still have
their IT architecture on this model, known as "the client/server" model.

![Client/Server Illustration](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_10C_ClientServerExample.png)

## Identify Which Role Possesses the Data That Browsers Display

The web was developed with a client/server model. Home PCs were relatively
underpowered _clients_ and web content sharing programs were installed on
high-power _servers_. Thus web _clients_ running _browser_ software were created
that would send a _request_ for a web page and the server would return the web
page.

![Web Application Stack](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_81_WebAppStack.png)

The specification on how _clients_ and _servers_ interact is called HTTP
(HyperText Transfer Protocol). This is why URLs start with `http://`: you're
telling the browser: "Browser, act as a client and use the HTTP standard to talk
to `flatironschool.com` and find a file called `index.html`." The browser
expresses this wish by transmitting a message that looks like:

`GET flatironschool.com /index.html`
![Browser as Client Illustration](https://curriculum-content.s3.amazonaws.com/html-basics/tour-of-the-web/Image_10D_BrowserClientInteraction.png)

Here it asks `flatironschool.com` for an HTML file called `index`. We'll explore
this _much_ more in subsequent lessons!

In return, the _server_ returns... HTML that's contained in the `index.html`
file.

## Identify What Type of Content Defines What's Seen in Browsers

Having been told which file on _its_ hard drive to consult, the web _server_
takes the contents of a file, pushes them across the internet _back_ to the
_client_. The client then receives the raw HTML. It looks something like this:

```html
<!DOCTYPE html>
<html lang="">
  <head>
    <title>Home | The Metropolitan Museum of Art</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="title" content="Home" />
    <meta
      name="keywords"
      content="Metropolitan Museum, Met, Metropolitan Museum of Art, Met Museum, Metropolitan"
    />
    <meta name="description" content="The Metropolitan Museum of Art is a..." />
    ...
  </head>
</html>
```

Obviously, this is _not_ what you see when you visit
[http://www.metmuseum.org](http://www.metmuseum.org). The difference hinges on
that special verb _render_. Your _client's_ browser _renders_ the "raw" HTML and
turns it into something _humans_ find nice to read.

And this is the essence of how the web works!

## Conclusion

In conclusion, we've talked about the history of the word _internet_ and how it
connects computers fulfilling _client_ and _server_ roles. We've identified that
_client_ machines use web browsers to make _requests_ of the _server_, according
to the HTTP standard, and the _server_ returns HTML data, stored on their hard
drives in files _back_ to the requesting _client_. The _client_ machine, running
browser software, then converts that raw HTML data into a _rendered_ format
which is what you experience as a web page.

As a summary, we've provided the following video that gives an introduction to
the web. If you are only interested in building web pages, you can stop at 3:48;
if you are studying a web programming technology e.g. Ruby or JavaScript, we
recommend watching the entire video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/7AS96jRnquI?rel=0&modestbranding=1" frameborder="0" allowfullscreen></iframe>

- [The Web in a Nutshell][twins]
- [Slides][]

## Resources

- [World Wide Web - Wikipedia](https://en.wikipedia.org/wiki/World_Wide_Web)
- [HTML basics - Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [An overview of HTTP - Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- [Static vs Dynamic](https://noahveltman.com/static-dynamic/)
- [Client Server Model - Wikipedia](https://en.wikipedia.org/wiki/Client%E2%80%93server_model)

[twins]: https://www.youtube.com/watch?v=7AS96jRnquI
[slides]:
  https://docs.google.com/presentation/d/1m6SPR13MdfF7YRhfx7HtvkOmFnrRyVQOEFgWhI8Bc0I/edit?usp=sharing
