<!DOCTYPE html>
<html lang="fi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>1714 – Portti</title>

  <style>
    body {
      margin: 0;
      font-family: Georgia, serif;
      background: url('tausta.jpg') center/cover no-repeat fixed;
      color: #e8d8b0;
      text-align: center;
    }

    .overlay {
      background: rgba(0, 0, 0, 0.65);
      min-height: 100vh;
      padding: 40px 20px;
    }

    h1 {
      font-size: 40px;
      letter-spacing: 2px;
      margin-top: 0;
    }

    p {
      font-size: 18px;
      opacity: 0.95;
      line-height: 1.6;
    }

    .key {
      margin-top: 40px;
      cursor: pointer;
      transition: transform 0.2s ease;
    }

    .key:hover {
      transform: scale(1.1);
    }

    #paper {
      display:
