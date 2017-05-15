# Ch. 2 Homework

__Create a recursive countdown function.__

[Link to working jsfiddle example](https://jsfiddle.net/meshuggie/t9bctdsL/)

```javascript
class App {
	constructor(i) {
  	this.str = ''
  	this.countdown(i)
  }
  countdown(i) {
    this.str += i + ' '
    if (i <= 1) {
      return
    }
    i--
    this.countdown(i)
  }
  get results() {
  	return this.str
  }
}

mocha.setup('bdd');
const expect = chai.expect;

describe('Recursive Countdown Function', function() {
	it('counts down from 5', function() {
  	const app = new App(5)
    expect(app.results).to.equal('5 4 3 2 1 ')
  });
});

mocha.run();

let app = new App(5)
document.getElementsByClassName('results')[0].innerHTML = app.results
```
