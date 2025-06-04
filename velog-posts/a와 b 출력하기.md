<h2 id="a와-b출력하기">a와 b출력하기</h2>
<hr />
<blockquote>
</blockquote>
<p>정수 a와 b가 주어집니다.
각 수를 입력받아 입출력 예와 같은 형식으로 출력하는 코드를 작성해 보세요.
제한사항
-100,000 ≤ a, b ≤ 100,000
코드를 입력하세요
입출력 예시
4   5
출력
a = 4
b = 5</p>
<h2 id="답안">답안</h2>
<pre><code>const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input = line.split(' ');
}).on('close', function () {
    console.log(&quot;a = &quot;+Number(input[0]) +&quot;\n&quot;+ &quot;b = &quot;+Number(input[1]));
});</code></pre>