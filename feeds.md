% XML and Content Management — RSS
% Heinz Wittenbrink
% 2. Mai 2017

## Zielsetzung

- RSS als Beispiel eines XML-Vokabulars verstehen
- Verwendungsmöglichkeiten eines XML-Formats verstehen
- Syntaktische und semantische Unterschiede ähnlicher XML-Formate verstehen
- Proprietäre und offene Alternativen verstehen

# Was ist RSS?

## Akronym und Auflösung
- **R**ich **S**ite **S**ummary
- **R**eally **S**imple **S** yndication

[History of RSS Infographic | aNewDomain.net | Pinterest](https://www.pinterest.com/pin/189432728049278934/ "History of RSS Infographic | aNewDomain.net | Pinterest")

[RSS - IndieWeb](https://indieweb.org/RSS "RSS - IndieWeb")

## Publizistische Konsequenzen von Feeds
- Lösung von Inhalten aus Publikationen
- Personalisierte Zusammenstellung von Inhalten
- Direkter Zugang zu Quellen
- Echtzeit-Informationen

## RSS in der Praxis: Feedreader

- [Bloglovin’](https://www.bloglovin.com/feed "Bloglovin’")
- [Feedly](https://feedly.com/i/my "Today / Me")

## RSS in der Praxis: Aggregation

- [Micro.blog](http://micro.blog/account/feeds "Micro.blog")
- [Our Examples - WP RSS Aggregator](https://www.wprssaggregator.com/live-demos/ "Our Examples - WP RSS Aggregator")

## RSS in der Praxis: Monitoring und SEO

- [Feedburner](https://feedburner.google.com/fb/a/dashboard?id=lb1m82guvp0jrko3pm89t166b8&gsessionid=nWj8iLiYmfLxmX24v_q4YjPN7hryA1o0 "Analyze :: Feed Stats Dashboard")

- [Official Google Webmaster Central Blog: Best practices for XML sitemaps & RSS/Atom feeds](https://webmasters.googleblog.com/2014/10/best-practices-for-xml-sitemaps-rssatom.html "Official Google Webmaster Central Blog: Best practices for XML sitemaps & RSS/Atom feeds")

## RSS in der Praxis: RSS als Austauschformat

- [How to Get an RSS Feed for Twitter, Instagram, Facebook, and Pinterest](https://zapier.com/blog/facebook-twitter-rss-feed/ "How to Get an RSS Feed for Twitter, Instagram, Facebook, and Pinterest")


## Beispiele für RSS-Dokumente

- [What Is RSS](https://www.xml.com/pub/a/2002/12/18/dive-into-xml.html "What Is RSS")

- [http://oer.fh-joanneum.at/contentstrategy/feed/](http://oer.fh-joanneum.at/contentstrategy/feed/)

## Elemente von RSS 2.0

- [RSS 2.0 specification](https://validator.w3.org/feed/docs/rss2.html "RSS 2.0 specification")
- Darstellung der Elemente von RSS 2.0

- ![Darstellung der RSS-Elemente](https://www.data2type.de/fileadmin/images/Newsfeeds_mit_RSS/RSS2.0-Elemente_Baumdiagramm.jpg "Darstellung der RSS-Elemente")

## Anbieten von Feeds

- Produktion im CMS
[WordPress Feeds « WordPress Codex](https://codex.wordpress.org/WordPress_Feeds "WordPress Feeds « WordPress Codex")
- Verlinken im HTML-Header

```
<link rel="alternate" type="application/rss+xml" title="CONTENT STRATEGY - Open Educational Resources &raquo; Feed" href="http://oer.fh-joanneum.at/contentstrategy/feed/" />
<link rel="alternate" type="application/rss+xml" title="CONTENT STRATEGY - Open Educational Resources &raquo; Kommentar-Feed" href="http://oer.fh-joanneum.at/contentstrategy/comments/feed/" />
```

## XML-Techologien: Schema

- [RSS 2.0 Schema - Source Code](https://rss2schema.codeplex.com/SourceControl/latest#schema/rss-2_0.xsd "RSS 2.0 Schema - Source Code")

## XML-Technologien: Namespaces
```
<?xml version="1.0" encoding="UTF-8"?><rss version="2.0"
	xmlns:content="http://purl.org/rss/1.0/modules/content/"
	xmlns:wfw="http://wellformedweb.org/CommentAPI/"
	xmlns:dc="http://purl.org/dc/elements/1.1/"
	xmlns:atom="http://www.w3.org/2005/Atom"
	xmlns:sy="http://purl.org/rss/1.0/modules/syndication/"
	xmlns:slash="http://purl.org/rss/1.0/modules/slash/"
	>

<channel>
	<title>CONTENT STRATEGY &#8211; Open Educational Resources</title>
	<atom:link href="http://oer.fh-joanneum.at/contentstrategy/feed/" rel="self" type="application/rss+xml" />
	<link>http://oer.fh-joanneum.at/contentstrategy</link>
	<description>Learning Materials for the M.A. Program in Content Strategy at the University of Applied Sciences Graz</description>
	<lastBuildDate>Sat, 29 Apr 2017 08:48:20 +0000</lastBuildDate>
	<language>de-DE</language>
	<sy:updatePeriod>hourly</sy:updatePeriod>
	<sy:updateFrequency>1</sy:updateFrequency>

	<item>
		<title>HTML5-Banner mit dem Google Web Designer</title>
		<link>http://oer.fh-joanneum.at/contentstrategy/html5-banner-mit-dem-google-web-designer/</link>
		<comments>http://oer.fh-joanneum.at/contentstrategy/html5-banner-mit-dem-google-web-designer/#respond</comments>
		<pubDate>Sat, 29 Apr 2017 07:03:21 +0000</pubDate>
		<dc:creator><![CDATA[Melanie Mitter]]></dc:creator>
```

# RSS 1.0

## Beispiel-Dokument 1:  [Pinboard-Feed](https://feeds.pinboard.in/rss/secret:16c05bf34b55b611cbb7/u:heinzwittenbrink/ "https://feeds.pinboard.in/rss/secret:16c05bf34b55b611cbb7/u:heinzwittenbrink/")

## Beispiel-Dokument 2:
[Grundstruktur eines RSS 1.0-Dokuments](https://www.data2type.de/xml-xslt-xslfo/newsfeeds-rss-atom/rss-1-0-und-rss-1-1/grundstruktur-rss-1-0-dokument/ "data2type GmbH: Grundstruktur eines RSS 1.0-Dokuments")


## RSS 1.0-Semantik

![RDF-Graph-des-Beispieldokuments1](https://www.data2type.de/fileadmin/images/Newsfeeds_mit_RSS/RDF-Graph-des-Beispieldokuments-1.png)
![RDF-Graph-des-Beispieldokuments2](https://www.data2type.de/fileadmin/images/Newsfeeds_mit_RSS/RDF-Graph-des-Beispieldokuments-2.png)

# RSS und Atom

## Technische Technische Unterschiede von RSS und Atom

- Einbetten von HTML-Inhalten
- Atom als Publikationsformat

## Der Atom-Standard

- Beispiel für ein Atom-Dokument:
[Grundstruktur eines Atom-Dokuments](https://www.data2type.de/xml-xslt-xslfo/newsfeeds-rss-atom/atom/aufbau-atom-feed/grundstruktur-atom-dokument/ "data2type GmbH: Grundstruktur eines Atom-Dokuments")


## Atom-Elemente
![Elemente eines Atom-Dokuments](https://www.data2type.de/fileadmin/images/Newsfeeds_mit_RSS/struktur-komplexes-atom-dokument-klein.png)

## XML-Technologien: Relax NG-Schemas

[Atom schema in RELAX NG XML Syntax Grammar](https://gist.github.com/tjdett/4617547 "Atom schema in RELAX NG XML Syntax Grammar")

# Alternativen zu XML-basierten Feedformaten

## JSON

- [JSON: What It Is, How It Works, & How to Use It - Copter Labs](https://www.copterlabs.com/json-what-it-is-how-it-works-how-to-use-it/ "JSON: What It Is, How It Works, & How to Use It - Copter Labs")

## Proprietäre APIs

- [Top 10 Social APIs: Facebook, Twitter and Google Plus | ProgrammableWeb](https://www.programmableweb.com/news/top-10-social-apis-facebook-twitter-and-google-plus/analysis/2015/02/17 "Top 10 Social APIs: Facebook, Twitter and Google Plus | ProgrammableWeb")

# RSS/Atom als offene Standards
## Freier Zugang zu Inhalten für Benutzer
- Unabhängigkeit von Applikationen/Anbietern
- Unabhängigkeit von Formatvorgaben

## Weiterentwicklung der Technologie in der Community
- Leichte Kombinierbarkeit mit anderen Technologien (z.B. Namespaces; Inhaltsformate)
- Entwicklung abgeleiteter Technologien (z.B. Podcasts, WebSub)

# Feeds in Content Management und Content-Strategie

## Content Management-Aufgaben ("Inhalt als Code")
- Produktion von Feeds sicherstellen
- Kontrolle der Feedformate und der Qualität von Feeds
- Monitoring von Feeds

## Contentstrategische und -taktische Aufgaben ("Code als Inhalt")
- Integration von Inhalten durch Feeds, Kuratieren
- Entscheidung über Inhalte, Umfang und Anzahl von Feeds
- Versorgen von Publikations-Plattformen mit Feeds
- Entscheidung über Kampagnen (siehe z.b. das [MailChimp RSS to Email Tutorial](https://blog.mailchimp.com/rss-to-email-tutorial/ "RSS to Email Tutorial"))
- Entscheidung über zusätzliche Angebote (Podcasts)
