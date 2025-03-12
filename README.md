<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>바카라 계산기</title>
</head>
<body>
    <h2>바카라 점수 계산기</h2>
    <label>카드 입력 (쉼표로 구분): </label>
    <input type="text" id="cards" placeholder="예: 10,3,7">
    <button onclick="calculateScore()">계산</button>
    <p id="result"></p>

    <script>
        function baccaratScore(cards) {
            let total = cards.reduce((sum, card) => sum + (card % 10), 0);
            return total % 10;
        }

        function calculateScore() {
            let input = document.getElementById("cards").value;
            let cards = input.split(",").map(Number);
            let score = baccaratScore(cards);
            document.getElementById("result").innerText = "바카라 점수: " + score;
        }
    </script>
</body>
</html>
