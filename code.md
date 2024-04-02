---
layout: code
title: Code
slug: /code
---

<style>
  .code-block figure {
    background-color: black;
    color: #F8F8F2; /* Adjust text color as needed */
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 20px;
    position: relative; /* Added to allow absolute positioning of line numbers */
  }

  .code-block figcaption {
    color: #50fa7b; /* Adjust caption color as needed */
    font-size: 16px;
    margin-bottom: 10px;
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
    background-color: #282a36; /* Adjust code background color as needed */
  }

  .code-line {
    position: absolute;
    left: 0;
    width: 30px; /* Adjust width as needed */
    text-align: right;
    color: #999; /* Adjust line number color as needed */
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
