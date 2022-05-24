# JS Style Guide

## Table of Contents
1. [Whitespace](#whitespace)
2. [Variables](#variables)
3. [Quotation Marks](#quotation-marks)
4. [Conditionals](#conditionals)
5. [Semi-Colons](#semi-colons)

## Whitespace
- Set tabs to "2 Spaces"

## Variables

- Use `const` declarations for all variable and function names unless there is a possibility that it will be reassigned. In the case of reassignment, use `let`.
- When naming variables and functions, make sure to to use clear descriptions of what that variable stores or does.
  - Boolean variables should begin with `is`. For example, `isRetro` reads as "is retro(grade) true?" 

## Quotation Marks
- Besides template literals and JSON test bodies, **single quotes** are used throughout JS code.

## Conditionals

### `if-else` Statements

- Short one-liner `if` statements can be written in one line.
```
if (pofFullDegree >= 360) pofFullDegree -= 360;

// as opposed to
if (pofFullDegree >= 360) {
  pofFullDegree -= 360;
}
```

- `else if` and `else` statements should begin on the same line as the previous block's closing curly bracket.
```
if (distanceBetween >= 0 && distanceBetween < 45) {
  moonPhaseName = "New Moon";
} else if (distanceBetween >= 45 && distanceBetween < 90) {
  moonPhaseName = "Crescent Moon";
} else if (distanceBetween >= 90 && distanceBetween < 135) {
  moonPhaseName = "First Quarter Moon";
} else {
   // ...
}
```

### Long Control Statements

- When a control statement becomes too long, break each group of conditions into a new line
  - For readability, keep logical operators at the beginning of each new the line
  - Closing parentheses and opening curly are also on their own new line

```
// Short Control
if (nice === 123 && short === 'abc') {
  someFunction();
}

// Long Control
if (
  (nice === 123 || short === 'abc')
  && (jk > 0 && iLied < 10)
  && haha === 'sorry'
) {
  someFunction();
}
```

### Ternaries

- Similarly to the above stated rules,
  - Ternaries with short controls and one line functions, can be written as one-liners.
  - Ternaries with long controls and/or multi-line code blocks will be broken into nested blocks beginning with `?` and `:`, and followed by a space.
```
const planet = 'mercury';
const mercury = isRetro ? true : false;
const moonPhase = getMoonPhase();

{planet === 'mercury && isRetro
  ? <div>
    <h1>Hello world,</h1>
    <p>Mercury is in retrograde.</p>
  </div>
  : moonPhase === 'full'
    ? <div>
      <h1>Good evening,</h1>
      <p>The moon is full.</p>
    </div>
    : <div>
       <h1>NO!</h1>
       <p>This is patrick!</p>
    </div>
}
```
**[⬆ back to top](#table-of-contents)**

## Semi-Colons

- Imports, variable declarations, and lines of code all end in a semi-colon.
- However certain _blocks_ of code do not. This includes:
  - Functions
  - If-else
  - For loops 

```
const sweph = require('sweph');

function celestialBodies(julianDayET, houseOrder) {
  for (let i = 0; i < cbData.length; i++) {
    const fullDegree = swephData[0];
	  const speed = swephData[3];
	  const cBody = ckObj(fullDegree, speed, cbData[i], houseOrder);
	  celestialBodies.push(cBody);

	  if (cbData[i].name === "true node") {
      let snFullDegree = cBody.fullDegree + 180;
      if (snFullDegree >= 360) snFullDegree -= 360;
      const snData = { name: "south node", type: "point" };
      let southNode = ckObj(snFullDegree, 0, snData, houseOrder);
      celestialBodies.push(southNode);
	  }
	}

  return celestialBodies;
}
```
**[⬆ back to top](#table-of-contents)**
