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
    padding-left: 40px; /* Added to accommodate line numbers */
    position: relative; /* Added for absolute positioning of line numbers */
  }

  .code-block code {
    display: block;
    padding: 10px;
    border-radius: 5px;
    color: black; /* Text color */
    background-color: transparent; /* No background */
  }

  .code-line {
    position: absolute;
    left: 0;
    width: 30px; /* Adjust width as needed */
    text-align: right;
    color: black; /* Line number color */
    padding-right: 10px;
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
