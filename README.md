<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>お問い合わせフォーム</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f8f8; /* 薄いグレーの背景 */
        }
        /* くすんだ赤のカスタムカラーを定義 */
        .bg-muted-red {
            background-color: #a05252; /* 例: テラコッタのような色 */
        }
        .text-muted-red {
            color: #a05252;
        }
        .border-muted-red {
            border-color: #a05252;
        }
        .hover\:bg-muted-red-dark:hover {
            background-color: #8b4545; /* ホバー時の少し濃い赤 */
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen p-4 sm:p-6 md:p-8">
    <div class="bg-white p-6 sm:p-8 md:p-10 rounded-xl shadow-lg w-full max-w-md mx-auto border-t-8 border-muted-red">
        <h2 class="text-2xl sm:text-3xl font-bold text-center mb-6 text-gray-800">お問い合わせ</h2>

        <form id="contactForm" class="space-y-6"
              action="https://docs.google.com/forms/u/0/d/e/1FAIpQLScfKIMLvla7euxG38MLTReBPil3035CMj-u-HoIKWw3dWYtqA/formResponse"
              method="POST"
              target="hidden_iframe"> <div>
                <label for="long_question" class="block text-gray-700 text-sm font-medium mb-2">
                    ご質問内容（詳細）
                </label>
                <textarea
                    id="long_question"
                    name="entry.722756462" rows="8"
                    class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-muted-red focus:border-transparent transition duration-200 ease-in-out resize-y"
                    placeholder="こちらにご質問や詳細をご記入ください。"
                ></textarea>
            </div>

            <button
                type="submit"
                class="w-full bg-muted-red text-white py-3 px-4 rounded-lg font-semibold text-lg
                       hover:bg-muted-red-dark focus:outline-none focus:ring-2 focus:ring-muted-red
                       focus:ring-offset-2 transition duration-200 ease-in-out shadow-md"
            >
                送信する
            </button>
        </form>

        <iframe name="hidden_iframe" id="hidden_iframe" style="display:none;" onload="if(submitted) {alert('お問い合わせが送信されました！'); document.getElementById('contactForm').reset(); submitted=false;}"></iframe>

        <script>
            let submitted = false; // フォームが送信されたかどうかを追跡するフラグ

            document.getElementById('contactForm').addEventListener('submit', function(event) {
                submitted = true; // フォーム送信時にフラグをtrueに設定
                // デフォルトのフォーム送信がiframeにリダイレクトされるため、
                // ここでpreventDefault()は呼び出しません。
                // iframeのonloadイベントでアラートとリセットを処理します。
            });
        </script>
    </div>
</body>
</html>
