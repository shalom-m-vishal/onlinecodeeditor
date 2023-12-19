<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Online Code Editor</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      height: 100vh;
      overflow: hidden;
    }

    #editor {
      flex: 1;
      height: 100%;
    }

    #output {
      flex: 1;
      height: 100%;
      overflow: auto;
      padding: 10px;
      background-color: #f1f1f1;
    }
  </style>
</head>
<body>
  <div id="editor">// Your code goes here</div>
  <div id="output"></div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.4.12/ace.js"></script>
  <script>
    var editor = ace.edit("editor");
    editor.setTheme("ace/theme/monokai");
    editor.getSession().setMode("ace/mode/javascript");

    editor.getSession().on('change', function () {
      var code = editor.getSession().getValue();
      document.getElementById('output').innerHTML = code;
    });
  </script>
</body>
</html>

