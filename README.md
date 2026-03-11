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
        .footer { margin-top: 30px; font-size: 0.8em; color: #7f8c8d; }
        
        #click_status { margin-top: 10px; color: #27ae60; font-weight: bold; min-height: 1.5em; }
        #main_button { padding: 8px 16px; cursor: pointer; background-color: #f8f9fa; border: 1px solid #ccc; border-radius: 4px; }
    </style>
</head>
<body>

<header>
    <h1>RPA Practice Site</h1>
    <p>「ブラウザフレームを切り替え」コマンドの検証用ページ</p>
</header>

<div class="container">
    <div class="frame-box" style="border-style: solid; border-color: #27ae60;">
        <div class="frame-label" style="color: #27ae60;">Main Content (フレーム外 / 親画面)</div>
        <p>ここはメインのドキュメントです。フレームに入る前にここを操作できます。</p>
        <button id="main_button" onclick="showClickResult()">メインのボタン</button>
        <div id="click_status"></div>
    </div>

    <div class="frame-box">
        <div class="frame-label">Frame Index: 0 (お問い合わせフォーム)</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#fffbe6;padding:10px;
