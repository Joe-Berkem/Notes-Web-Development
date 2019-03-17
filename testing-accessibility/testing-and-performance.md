# CSS Testing & Performance
---

**Testing for finished site**
Different browsers
Accessibility testing 
Different browsers
Speed 
Code validation
Real life/ UX

**Testing while coding**
Linting
Unit Test 
Test DD

## Cross Browser & cross device
Big 5 = Safari, firefox, chrome, opera, ie/edge

caniuse.com


@supports 
acts like a media query
can contain grid

@supports not { css property}
can contain all fallback code!


Lazy loading
using javascipt to fetch high res image after low res quick image is showed at first paint!

## Testing your code
---

### Cross browser & cross device

- Testing on different browsers & devices
- Browser testing tools
	- [https://www.browserstack.com/](https://www.browserstack.com/) |
	- [https://crossbrowsertesting.com/pricing](https://crossbrowsertesting.com/pricing) |
	- [https://www.browserling.com/](https://www.browserling.com/) |
	- Dev tools |

---

## Aside: Browser support

---

### Loads of different browsers out there

- Loads of different CSS & HTML specs (& JavaScript too!)
- Things may not be supported |
- Things may render differently |
- Things may be old |
- Things may be new |

---

### Can I use?

[caniuse.com](www.caniuse.com)

---

### What if I want to use something new & support old browsers?

- Polyfills
- `@supports`
- Have your website work without it

---

### Remember Modernizr

[https://modernizr.com/](https://modernizr.com/)

Detect features, add classes, harness this to add support/polyfills

---

### Validate your code

- HTML [https://validator.w3.org/](https://validator.w3.org/)
- CSS [https://jigsaw.w3.org/css-validator/](https://jigsaw.w3.org/css-validator/)

---

### Accessibility

- Wave accessibility check [https://wave.webaim.org/](https://wave.webaim.org/)

---

### Devtools Audit

- Google Lighthouse
	- Devtools Go to `Audits` tab

---

## Aside: Performance

---

### Data

Network: Modems, 2G, 3G, 4G, Broadband, Cable

Everything that makes an app or website is made of data, that data needs to be served over the network

Thus it needs to be downloaded

---

### But why tho?

- Users don’t like waiting (2 secs max)
- Users have data plans |
- Users may not have good connections |

---

### So?

- Users == Money/Revenue
- Amazon reduce their load speed by 1ms - reduce revenue by 1% |

---

### How

- Write good *concise* DRY code
- Asset management
	- Compress images
	- Lazy loading
- First paint

Note: There are many many techniques to do with performance - you will learn a lot more of this over your career, but suffice to say start with good clean code

---

## Back to testing

---
# Testing Links

---

### Cross browser & cross device

- Testing on different browsers & devices
- Browser testing tools
	- [https://www.browserstack.com/](https://www.browserstack.com/)
	- [https://crossbrowsertesting.com/pricing](https://crossbrowsertesting.com/pricing)
	- [https://www.browserling.com/](https://www.browserling.com/)
	- Dev tools

---

### Validate your code

- HTML [https://validator.w3.org/](https://validator.w3.org/)
- CSS [https://jigsaw.w3.org/css-validator/](https://jigsaw.w3.org/css-validator/)

---

### Accessibility

- Wave accessibility check [https://wave.webaim.org/](https://wave.webaim.org/)

---

### Audit

- Check your website via the audit tool in devtools

---

### Real life

Have a look at it on **your browsers** and on **your mobile**





### All the links

[Are here 🤓](https://github.com/develop-me/fellowship-wk1-beg-html-css/blob/master/day05/01TestingAndPerformance/README.md)





