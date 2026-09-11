<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
</head>
<body>

<h1>Step-by-Step Guide: How to Extract and Import Pangea API Requests into Postman</h1>

<p>This guide provides instructions on how to capture a search request from the Pangea portal using browser Developer Tools and execute it inside Postman.</p>

<h2>About Pangea</h2>
<blockquote>
<p><strong>Pangea</strong> <em>is a search engine developed for the Brazilian Judiciary (PDPJ) that unifies research on qualified legal precedents. It enables legal professionals to quickly query binding decisions, court precedents, and case law across various Brazilian courts.</em></p>
</blockquote>

<h3>1. Access the Pangea Portal</h3>
<p><em>Prerequisite: use browsers like Google Chrome, Microsoft Edge, or Brave.</em></p>
<ol>
  <li>Open your browser of choice.</li>
  <li>Go to the official portal address: <a href="https://pangeabnp.pdpj.jus.br/pesquisa">https://pangeabnp.pdpj.jus.br/pesquisa</a>.</li>
</ol><img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5479dded-4621-4698-8cbb-535884c7fa91" />


<h3>2. Configure Search Filters</h3>
<ol>
  <li>On the main screen, select your desired search parameters and filters.</li>
  <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/57a21c56-dff0-4d44-b3e4-8d106de15081" />

  <li>Note: Do not click "Search" yet.</li>
</ol>

<h3>3. Open Developer Tools</h3>
<ol>
  <li>Press the <code>F12</code> key on your keyboard (or press <code>Ctrl + Shift + I</code> / <code>Cmd + Option + I</code> on Mac).</li>
  <li>In the panel that opens, navigate to the <strong>Network</strong> tab.</li>
  <img width="783" height="411" alt="image" src="https://github.com/user-attachments/assets/0d374c67-e52f-4b6b-a79c-8ac35df72611" />

  <li>In the Network filters, select the <strong>Fetch/XHR</strong> option to filter API requests only.</li>
  <img width="782" height="413" alt="image" src="https://github.com/user-attachments/assets/ace42d6f-212f-4488-a3d4-15478aef1f80" />

</ol>

<h3>4. Execute the Search and Capture the Request</h3>
<ol>
  <li>Return to the web page and click the button to Apply Filter (or Search).</li>
  <li>In the list of network requests, look for the line labeled <code>precedentes</code>.</li>
  <li>Right-click on the <code>precedentes</code> request line.</li>
  <li>Hover over <strong>Copy</strong> and select <strong>Copy as cURL (bash)</strong>.</li>
</ol>

<h3>5. Save and Import into Postman</h3>
<ol>
  <li>Open a text editor (such as Notepad or TextEdit) and paste the copied content (<code>Ctrl + V</code>).</li>
  <img width="717" height="444" alt="image" src="https://github.com/user-attachments/assets/3bed738b-f7f9-45ed-aa56-e25a586dc215" />

  <li>Save the file on your computer as a text file (e.g., <code>pangea_request.txt</code> or <code>.sh</code>).</li>
  <li>Open Postman.</li>
  <li>Click the <strong>Import</strong> button in the top left corner, or drag and drop the text file directly into the Postman interface.
<img width="1364" height="716" alt="image" src="https://github.com/user-attachments/assets/9a3b78ff-9854-448b-8a8a-1d42443f7fa4" />

  </li>
</ol>

<h3>6. Run the Request and View Data</h3>
<ol>
  <li>Once Postman automatically parses the cURL request, click the <strong>Send</strong> button.</li>
  <img width="723" height="392" alt="image" src="https://github.com/user-attachments/assets/6d4d9772-11b6-4734-99d1-e639cc1479bc" />

  <li>The structured data response (typically in JSON format) will be displayed in the lower panel.</li>
  <img width="720" height="384" alt="image" src="https://github.com/user-attachments/assets/16e44cf1-aecf-4a6d-8e68-3fe4ad83090a" />

</ol>

</body>
</html>
