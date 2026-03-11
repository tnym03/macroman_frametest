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
    </style>
</head>
<body>

<header>
    <h1>RPA Practice Site</h1>
    <p>「ブラウザフレームを切り替え」コマンドの検証用ページ</p>
</header>

<div class="container">
    <div class="frame-box">
        <div class="frame-label">Frame Index: 0 (お問い合わせフォーム)</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#fffbe6;padding:10px;}</style>
            <h3>お問い合わせ</h3>
            <p>お名前：<input type="text" id="name_input" placeholder="ここに入力"></p>
            <button onclick="alert(\"送信完了\")">送信</button>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Frame Index: 1 (ニュース)</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#eef9ff;padding:10px;}</style>
            <h3>最新ニュース</h3>
            <ul>
                <li>RPA導入で業務効率化！</li>
                <li>フレーム切り替えのコツとは？</li>
            </ul>
            <a href="#" id="news_link">詳細を見る</a>
        '></iframe>
    </div>

    <div class="frame-box">
        <div class="frame-label">Frame Index: 2 (アンケート)</div>
        <iframe srcdoc='
            <style>body{font-family:sans-serif;background:#f9f0ff;padding:10px;}</style>
            <h3>満足度調査</h3>
            <input type="radio" name="star" id="star5"> <label for="star5">満足</label><br>
            <input type="radio" name="star" id="star1"> <label for="star1">不満</label>
        '></iframe>
    </div>

    <div class="frame-box" style="border-style: solid; border-color: #27ae60;">
        <div class="frame-label" style="color: #27ae60;">Main Content (フレーム外)</div>
        <p>ここはメインのドキュメントです。</p>
        <button id="main_button">メインのボタン</button>
    </div>
</div>

<div class="footer">
    ※各フレーム内を操作する前に、必ず「ブラウザフレームを切り替え」コマンドを実行してください。
</div>

</body>
</html>
