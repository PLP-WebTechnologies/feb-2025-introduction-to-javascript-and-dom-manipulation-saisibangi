/*Introduction to JavaScript and DOM Manipulation Assignment*/
/*index.html*/
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript DOM Example</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1 id="main-heading">Welcome to dynamic page</h1>
  </header>

  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </nav>

  <main>
    <section>
      <p id="text-content">This paragraph will change dynamically.</p>
      <button onclick="changeText()">Change Text</button>
      <button onclick="changeStyle()">Change Style</button>
    </section>
    <section>
      <button onclick="addElement()">Add Element</button>
      <button onclick="removeElement()">Remove Element</button>
      <div id="dynamic-container"></div>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 Example Website</p>
  </footer>
  <script src="script.js"></script>
</body>
</html>
/*script.js*/
function changeText() 
{
  const paragraph = document.getElementById('text-content');
  paragraph.textContent = "The text has been changed using JavaScript!";
}
function changeStyle() {
  const heading = document.getElementById('main-heading');
  heading.style.color = 'darkblue';
  heading.style.fontSize = '2.5em';
  heading.style.backgroundColor = '#f0f8ff';
  heading.style.padding = '10px';
}
function addElement() {
  const container = document.getElementById('dynamic-container');
  const newElement = document.createElement('p');
  newElement.textContent = "This paragraph was added dynamically.";
  newElement.id = "dynamic-paragraph";
  container.appendChild(newElement);
}
function removeElement() {
  const element = document.getElementById('dynamic-paragraph');
  if (element) {
    element.remove();
  } else {
    alert("No dynamic element to remove!");
  }
}
/*styles.css (for better visuals)*/
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}
button {
  margin: 5px;
  padding: 10px;
  cursor: pointer;
}
