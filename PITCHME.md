#HSLIDE
# Functional JavaScript / Linq for JS
    C#  | JS  | Support <!-- .element: class="fragment" -->
    --- | --- | -------
    Where | filter | ES5
    Select | map | ES5 <!-- .element: class="fragment" -->
    Aggregate | reduce | ES5 <!-- .element: class="fragment" -->
    => | => | ES6 <!-- .element: class="fragment" -->

#VSLIDE
```javascript
let dogs = [
    {name: 'spot', age: 7},
    {name: 'duke', age: 1},
    {name: 'samson', age: 2}
];

let puppies = dogs.filter(x => x.age < 3).map(x => x.name);
// ['duke','samson']
```

#HSLIDE
# Reactive C# & JS
<!-- http://www.slideshare.net/Codemotion/tamir-dresher-reactive-extensions-rx-101 -->
    Linq for events
<!--IObserver & IObservable<T>-->

#VSLIDE
```csharp
var textChanged = Observable.FromEventPattern(txtBox, "TextChanged")
    .Select(txtBox => txtBox.Text);

textChanged
    .Where(txt => txt.Length > 3)
    .Throttle(TimeSpan.FromSeconds(0.5))
    .DistinctUnitlChanged()
    .SelectMany(txt => SearchAsync(txt))
    .Switch()
    .Subscribe(/* update page */);

```

#VSLIDE
```javascript
var $input = $('#input');

Rx.Observable.fromEvent($input, 'keyup')
    .map(e => e.target.value)
    .filter(txt => txt.length > 3)
    .throttle(500 /*ms*/)
    .distinctUnitlChanged()
    .flatMapLatest(searchWikipedia)
    .subscribe(data => {
        /* update page */
    }, error => {
        /* show error */
    });
```
<!-- stock example -->

#HSLIDE
# IOT
    * Alexa has skills (apps) that you can program <!-- .element: class="fragment" -->
    * Connect Alexa to www.particle.io with skill <!-- .element: class="fragment" -->
    * Connect www.particle.io to Particle Photon ($19), Raspberry Pi ($35), Raspberry Pi Zero ($5) <!-- .element: class="fragment" -->
    * Connect Alexa to Tesla <!-- .element: class="fragment" -->

#VSLIDE
![Photon](http://cdn.shopify.com/s/files/1/0925/6626/products/150802_Particle-26_large.jpg?v=1449089167)

#VSLIDE
![Raspberry Pi 3](https://www.raspberrypi.org/wp-content/uploads/2016/02/Raspberry-Pi-3-top-down-web.jpg)

#VSLIDE
![Raspberry Pi Zero](https://www.raspberrypi.org/wp-content/uploads/2016/02/Raspberry-Pi-Zero-web.jpg)

#HSLIDE
# Dates and Time
    Timezones change every year <!-- .element: class="fragment" -->
        At least 10 time zone changes in 2016
        Egypt scrapped DST 3 days before it would have started
        In 2011 Samoa switched sides of international date line, skips day
    Current and past timestamps, always use UTC <!-- .element: class="fragment" -->
    Furture datetime, use local datetime <!-- .element: class="fragment" -->
    Birthdays, start/end dates, use date object without time component <!-- .element: class="fragment" -->
    Format date yyyy-MM-dd, provide help text <!-- .element: class="fragment" -->
    Don't write your own lib, moment.js, Noda Time <!-- .element: class="fragment" -->
    Mock the clock <!-- .element: class="fragment" -->
    iana.org/time-zones Internet Assigned Numbers Authority <!-- .element: class="fragment" -->

#HSLIDE
# Domain Driven Apps
    Ubiquitous Language: Keep same names for work items, features, models, db objects <!-- .element: class="fragment" -->
    Bounded Context: Keep your data and models to yourself <!-- .element: class="fragment" -->
    Aggregate: Groups of immuteable objects <!-- .element: class="fragment" -->
    Clean Architecture / Onion Architecture:  <!-- .element: class="fragment" -->

#VSLIDE
![Onion Architecture](http://blog.thedigitalgroup.com/chetanv/wp-content/uploads/sites/23/2015/07/image1.png)

#HSLIDE
#HSLIDE
#HSLIDE
# Security
    SSL is broken, use TLS 1.2 if possible <!-- .element: class="fragment" -->
    let's encrypt has free certs <!-- .element: class="fragment" -->
    firefox and chrome are marking http sites as unsecure <!-- .element: class="fragment" -->
    http2 requires TLS <!-- .element: class="fragment" -->
    password storage is tough to get right and requires changing the computational intenity every year <!-- .element: class="fragment" -->
    use azure AD, B2B, B2C <!-- .element: class="fragment" -->
    Phyisical security <!-- .element: class="fragment" -->
    think like a hacker <!-- .element: class="fragment" -->
    the internet is being scanned <!-- .element: class="fragment" -->
        MassScan <!-- .element: class="fragment" -->
        Shodan.io <!-- .element: class="fragment" -->
        Censys.io <!-- .element: class="fragment" -->
        Google <!-- .element: class="fragment" -->
    break the rules <!-- .element: class="fragment" -->
    Rubber Ducky Usb drive <!-- .element: class="fragment" -->
    AFL, Burp, OWASP Zed Attack Proxy, BeFF, WSFuzzer <!-- .element: class="fragment" -->
    
#HSLIDE
# Failure
    Learn from failure, hubble & mars climate orbiter <!-- .element: class="fragment" -->
    Narrow focus, new coke <!-- .element: class="fragment" -->
    stopping at success, myspace <!-- .element: class="fragment" -->
    survivorship bais, only looking at success cases <!-- .element: class="fragment" -->
    lucky people try new things <!-- .element: class="fragment" -->
    Sometimes success is luck, bubble wrap, sticky notes, play-doh, safety glass <!-- .element: class="fragment" -->
    don't blame and shame, give grace <!-- .element: class="fragment" -->
    take advantage of failures <!-- .element: class="fragment" -->
    take risks and learn <!-- .element: class="fragment" -->
    FAIL - Frist Attempt In Learning <!-- .element: class="fragment" -->
    Fail fast, learn fast <!-- .element: class="fragment" -->
    Failure is not falling down but refusing to get up <!-- .element: class="fragment" -->

#HSLIDE
# UI
    Make things closer and bigger to users to get them to find and click <!-- .element: class="fragment" -->
    Take into account how we hold our gadgets <!-- .element: class="fragment" -->
    watch users use the system for the first time <!-- .element: class="fragment" -->
    more choices = more time, so reduce choices <!-- .element: class="fragment" -->
    You can only hold 7-ish items in your head <!-- .element: class="fragment" -->

#HSLIDE
# Virtual DOM
```javscript
    {
        tag: div,
        children: [
            {tag: input, attributes: [ {value: 'hi'} ]}
        ]
    }
```
<!-- # Angular 2 -->