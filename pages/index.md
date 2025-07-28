---
title: Correct Math Answers
layout: page
foot: questions-js.html
---

{% capture tag %}
Do you need to know [`2 + 2`]({{ '/answers.html?q=2%2B2' | relative_url }}){:.bg-primary-subtle .px-1 .rounded}, [`6 - 4`]({{ '/answers.html?q=6-4' | relative_url }}){:.bg-primary-subtle .px-1 .rounded}, [`10 * -5`]({{ '/answers.html?q=10*-5' | relative_url }}){:.bg-primary-subtle .px-1 .rounded}, or [`99 / 678493`]({{ '/answers.html?q=99%2F678493' | relative_url }}){:.bg-primary-subtle .px-1 .rounded}? We've got you covered! And you don't need a calculator.
{:.lead}

If you need correct answers to math questions this site will provide exactly what you need.
{:.lead}
{% endcapture %}
{% include jumbotron.html heading=site.title text=tag button-text="Learn More" button-link="about.html" bg="info-subtle" %}

## Ask Your Math Question

<div class="p-3 mb-3">
    <form class="row g-3 align-items-center mb-4" id="mathForm" action="/answers.html" method="get">
    <div class="col-auto">
        <input type="number" class="form-control" id="number1" placeholder="First number" required>
    </div>
    <div class="col-auto">
        <select class="form-select" id="operator" required>
        <option value="+">+</option>
        <option value="-">−</option>
        <option value="*">×</option>
        <option value="/">/</option>
        </select>
    </div>
    <div class="col-auto">
        <input type="number" class="form-control" id="number2" placeholder="Second number" required>
    </div>
    <div class="col-auto">
        <button type="submit" class="btn btn-success">Submit</button>
    </div>
    </form>
</div>
<script>
document.getElementById('mathForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const n1 = document.getElementById('number1').value;
  let op = document.getElementById('operator').value;
  // Use * for x and / for ÷ in query string
  if (op === '×') op = '*';
  if (op === '÷') op = '/';
  const n2 = document.getElementById('number2').value;
  const query = encodeURIComponent(`${n1}${op}${n2}`);
  window.location.href = `{{ '/answers.html' | relative_url }}?q=${query}`;
});
</script>

## Example Questions

Do you know the correct answers to these good math questions?

<div id="questionsdiv" class="mb-5"></div>


