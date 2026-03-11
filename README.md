<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>RPA検証用：フレーム切り替えテスト</title>
    <style>
        body { font-family: sans-serif; background-color: #f4f7f6; margin: 20px; color: #333; }
        header { background: #2c3e50; color: white; padding: 15px; border-radius: 8px; margin-bottom: 20px; }
        .container { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        .frame-box { border: 2px dashed #95a5a6; padding: 10px; background: white; border-radius: 8px; }
        .frame-label { font-weight: bold; color: #e67e22; margin-bottom: 5px; }
        iframe { width: 100%; height: 200px; border: 1px solid #ddd; border-radius: 4px; }
        /* ボタンとメッセージのスタイル */
        #main_button { padding: 8px 15px; cursor: pointer; }
        #click_status { margin-top: 10px; color: #d35400; font-weight: bold; height: 1.2em; }
    </style>
</head>
<body>

<header>
    <h1>RPA Practice Site</h1>
    <p>「ブラウザフレームを切り替え」コマンドの検証用ページ</p>
</header>

<div class="container">
    <div class="frame-box">
        <div class="frame-label">Frame Index: 0</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#fffbe6;padding:10px;}</style>
            <h3>Frame 0</h3>
            <p>名前：<input type="text" id="name_input"></p>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Frame Index: 1</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#eef9ff;padding:10px;}</style>
            <h3>Frame 1</h3>
            <button onclick="alert(\"Frame 1 Clicked\")">Frame Button</button>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Frame Index: 2</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#f9f0ff;padding:10px;}</style>
            <h3>Frame
