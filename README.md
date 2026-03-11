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
        
        /* メインボタン用のスタイル */
        #main_button { 
            padding: 10px 20px; background-color: #27ae60; color: white; 
            border: none; border-radius: 5px; cursor: pointer; font-size: 16px;
        }
        #main_button:hover { background-color: #219150; }
        #message_area { margin-top: 10px; font-weight: bold; color: #c0392b; min-height: 1.2em; }
    </style>
</head>
<body>

<header>
    <h1>RPA Practice Site</h1>
    <p>「ブラウザフレームを切り替え」コマンドの検証用ページ</p>
</header>

<div class="container">
    <div class="frame-box">
        <div class="frame-label">Index: 0 / ID: id_contact</div>
        <iframe id="id_contact" name="name_contact" srcdoc='
            <style>body{font-family:sans-serif;background:#fffbe6;padding:10px;}</style>
            <h3>お問い合わせ</h3>
            <p>名前：<input type="text" id="name_input" placeholder="ここに入力"></p>
            <button>送信</button>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Index: 1 / ID: id_news</div>
        <iframe id="id_news" name="name_news" srcdoc='
            <style>body{font-family:sans-serif;background:#eef9ff;padding:10px;}</style>
            <h3>最新ニュース</h3>
            <a href="#" id="news_link">詳細を見る</a>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Index: 2 / ID: id_survey</div>
        <iframe id="id_survey" name="name_survey" srcdoc='
            <style>body{font-family:sans-serif;background:#f9f0ff
