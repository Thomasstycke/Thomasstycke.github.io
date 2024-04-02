---
layout: code
title: Code
slug: /code
---

<style>
  .code-block figure {
    border: 2px solid black; /* Black border */
    border-radius: 5px;
    margin-bottom: 20px;
    position: relative; /* Added to allow absolute positioning of line numbers */
  }

  .code-block figcaption {
    display: none; /* Hide the caption */
  }

  .code-block pre {
    margin: 0;
    padding-left: 35px; /* Adjusted to reduce space between line numbers and code */
    position: relative; /* Added for absolute positioning of line numbers */
  }

  .code-block code {
    display: block;
    padding: 10px;
    border-radius: 5px;
    color: black; /* Text color */
    background-color: transparent; /* No background */
    font-size: 12px; /* Adjust font size to match line index size */
    line-height: 1.2; /* Adjust line height */
  }

  .code-line {
    position: absolute;
    left: 5px; /* Adjusted to reduce distance from the edge */
    width: 30px; /* Adjust width as needed */
    text-align: right;
    color: black; /* Line number color */
    font-size: 12px; /* Adjust font size to match code size */
    padding-right: 5px; /* Adjusted to reduce distance from code */
    pointer-events: none; /* Ensures line numbers do not interfere with text selection */
  }
</style>

<div class="code-block">
  <figure>
    <figcaption>Figure 1: Python Code</figcaption>
    <pre><code class="python">
    <span class="code-line">1</span> # Your Python code goes here
    <span class="code-line">2</span> def hello_world():
    <span class="code-line">3</span>     print("Hello, world!")
    <span class="code-line">4</span> 
    <span class="code-line">5</span> hello_world()
    </code></pre>
  </figure>
</div>
