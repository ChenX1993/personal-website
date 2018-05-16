# Personal Website New Version

This is my new personal website.

### Performance Optimization

Several optimization on performance have been applied so that the web page can be loaded faster

+ Load images after page is presented, user data-src to store url

```javascript
window.onload = function () {
    [].forEach.call(document.querySelectorAll("img[data-src]"), function (a) {
        a.setAttribute("src", a.getAttribute("data-src"));
        a.onload = function () {
            a.removeAttribute("data-src")
        }
    })
};
```

+ Load css animation in body using Javascript so it will not block the parsing of DOM

#### Add weather report

 On the top of the page, weather report is displayed according to users' location. This part including a simple css animation and a text notification. There are 2 steps to implement this function. First is to query an ip to location API. And than querying the weather api by location. Because there is a small delay from DOM loaded to weather report to display. An opacity transition is applied to smooth the animation.

### SEO 

To do the search engine optimization, following tips are applied:

+ Content Best Practices
  + Document has a `<title>` element
  + Document has a meta description
  + Document has a valid `hreflang`
+ Mobile friendly
  - Has a <meta name="viewport"> tag with  width or initial-scale
  - Document uses legible font sizes
+ Use structured data

```javascript
{
    "@context": "http://schema.org",
    "@type": "Person",
    "name": "Yang Shi",
    "jobTitle": "Student",
    "url": "http://ys2843.com",
    "sameAs": [
        "https://github.com/ys2843",
        "https://www.linkedin.com/in/yang-shi-591056135/",
        "https://www.facebook.com/profile.php?id=100007728030651"
    ],
    "gender": "male",
    "birthDate": "1994-06-04",
    "image": "./images/avatar.jpg"
}
```

