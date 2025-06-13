<h3 id="1-특수문자-출력">1. 특수문자 출력</h3>
<p>다음과 같이 특수문자를 그대로 출력하도록 <code>solution</code> 함수를 작성해주세요.</p>
<blockquote>
<pre><code class="language-js">function solution() {
  console.log(&quot;!@#$%^&amp;*(\\\'\&quot;&lt;&gt;?:;&quot;);
} // 특수문자 출력 시 이스케이프 문자 처리에 주의</code></pre>
</blockquote>
<hr />
<h3 id="2-덧셈식-출력">2. 덧셈식 출력</h3>
<p><code>a</code>, <code>b</code>가 주어질 때 덧셈 결과를 'a + b = c' 형식으로 출력하는 함수를 완성해주세요.</p>
<blockquote>
<pre><code class="language-js">function solution(a, b) {
  console.log(`${a} + ${b} = ${a + b}`);
} // 템플릿 리터럴을 사용하면 문자열 안에서 변수 삽입이 쉬움</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (a, b) =&gt; console.log(`${a} + ${b} = ${a + b}`); // 템플릿 리터럴 사용</code></pre>
</blockquote>
<hr />
<h3 id="3-문자열-합치기">3. 문자열 합치기</h3>
<p><code>str1</code>, <code>str2</code>가 주어질 때 두 문자열을 붙여서 반환하는 함수를 작성해주세요.</p>
<blockquote>
<pre><code class="language-js">function solution(str1, str2) {
  return str1 + str2;
} // 문자열 덧셈으로 연결</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (str1, str2) =&gt; str1 + str2; // 간단한 연결 표현</code></pre>
</blockquote>
<hr />
<h3 id="4-문자열-돌리기">4. 문자열 돌리기</h3>
<p>문자열 <code>str</code>이 주어졌을 때 각 문자를 한 줄씩 출력하는 함수를 작성해주세요.</p>
<blockquote>
<pre><code class="language-js">function solution(str) {
  [...str].forEach(ch =&gt; console.log(ch));
} // spread 문법으로 문자 배열화</code></pre>
</blockquote>
<hr />
<h3 id="5-짝수-홀수-구분">5. 짝수 홀수 구분</h3>
<p>자연수 <code>n</code>이 주어졌을 때 짝수면 &quot;even&quot;, 홀수면 &quot;odd&quot;를 출력하는 함수를 작성해주세요.</p>
<blockquote>
<pre><code class="language-js">function solution(n) {
  console.log(`${n} is ${n % 2 === 0 ? 'even' : 'odd'}`);
} // 삼항 연산자와 템플릿 리터럴 사용</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = n =&gt; console.log(`${n} is ${n % 2 === 0 ? 'even' : 'odd'}`);</code></pre>
</blockquote>
<hr />
<h3 id="6-문자열-겹쳐쓰기">6. 문자열 겹쳐쓰기</h3>
<p><code>my_string</code>, <code>overwrite_string</code>, <code>s</code>가 주어질 때 my_string의 s번째부터 overwrite_string으로 덮어쓴 결과를 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(my_string, overwrite_string, s) {
  return my_string.slice(0, s) + overwrite_string + my_string.slice(s + overwrite_string.length);
} // 문자열 덮어쓰기: 앞 + 덮어쓴 문자열 + 뒤 잘라 붙이기</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (str, over, s) =&gt; str.slice(0, s) + over + str.slice(s + over.length);</code></pre>
</blockquote>
<hr />
<h3 id="7-두-수의-연산값-비교">7. 두 수의 연산값 비교</h3>
<p><code>a</code>, <code>b</code>가 주어질 때 <code>a + b</code>와 <code>2 * a * b</code> 중 더 큰 값을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(a, b) {
  return Math.max(a + b, 2 * a * b);
} // Math.max()를 사용하면 간결하게 비교 가능</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (a, b) =&gt; Math.max(a + b, 2 * a * b);</code></pre>
</blockquote>
<hr />
<h3 id="8-몫-구하기">8. 몫 구하기</h3>
<p><code>num1</code>, <code>num2</code>가 주어질 때 <code>num1</code>을 <code>num2</code>로 나눈 몫을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(num1, num2) {
  return Math.floor(num1 / num2);
} // 소수점 버림은 Math.floor()</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (a, b) =&gt; Math.floor(a / b);</code></pre>
</blockquote>
<hr />
<h3 id="9-배수-확인">9. 배수 확인</h3>
<p><code>num</code>, <code>n</code>이 주어졌을 때 <code>num</code>이 <code>n</code>의 배수면 1, 아니면 0을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(num, n) {
  return num % n === 0 ? 1 : 0;
} // 나머지 연산자와 삼항 연산자 조합</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (num, n) =&gt; +(num % n === 0);</code></pre>
</blockquote>
<hr />
<h3 id="10-공배수-확인">10. 공배수 확인</h3>
<p><code>number</code>, <code>n</code>, <code>m</code>이 주어졌을 때 두 수의 공배수면 1, 아니면 0을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(number, n, m) {
  return number % n === 0 &amp;&amp; number % m === 0 ? 1 : 0;
} // &amp;&amp;로 공배수 조건 확인</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (number, n, m) =&gt; +(number % n === 0 &amp;&amp; number % m === 0);</code></pre>
</blockquote>
<hr />
<h3 id="11-flag에-따라-다른-계산">11. flag에 따라 다른 계산</h3>
<p><code>a</code>, <code>b</code>, <code>flag</code>가 주어졌을 때 flag가 true면 더하고 false면 빼세요.</p>
<blockquote>
<pre><code class="language-js">function solution(a, b, flag) {
  return flag ? a + b : a - b;
} // 조건에 따라 연산 선택</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (a, b, f) =&gt; f ? a + b : a - b;</code></pre>
</blockquote>
<hr />
<h3 id="12-양꼬치-가격-계산">12. 양꼬치 가격 계산</h3>
<p><code>n</code>, <code>k</code>가 주어질 때, 10인분당 1개 음료가 무료일 때 전체 비용을 구하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(n, k) {
  return n * 12000 + (k - Math.floor(n / 10)) * 2000;
} // 서비스 음료 제외한 수량만 곱하기</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (n, k) =&gt; n * 12000 + (k - Math.floor(n / 10)) * 2000;</code></pre>
</blockquote>
<hr />
<h3 id="13-코드-처리하기">13. 코드 처리하기</h3>
<p><code>code</code> 문자열을 순회하며 모드에 따라 홀/짝 인덱스 문자를 필터링해 출력하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(code) {
  let mode = 0;
  let ret = '';
  for (let i = 0; i &lt; code.length; i++) {
    if (code[i] === '1') mode = 1 - mode;
    else if (i % 2 === mode) ret += code[i];
  }
  return ret || 'EMPTY';
} // 모드 스위칭과 인덱스 필터링</code></pre>
</blockquote>
<hr />
<h3 id="14-등차수열의-특정-항까지-더하기">14. 등차수열의 특정 항까지 더하기</h3>
<p><code>a</code>, <code>d</code>, <code>included</code> 배열이 주어질 때, true인 항만 등차수열로 계산해 더하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(a, d, included) {
  return included.reduce((acc, val, i) =&gt; val ? acc + (a + d * i) : acc, 0);
} // reduce로 누적 합</code></pre>
</blockquote>
<hr />
<h3 id="15-문자-리스트를-문자열로-변환하기">15. 문자 리스트를 문자열로 변환하기</h3>
<p><code>arr</code> 배열에 담긴 문자열 요소들을 순서대로 이어붙여 하나의 문자열로 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(arr) {
  return arr.join(&quot;&quot;);
} // join 메서드로 배열 요소 이어붙이기</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = arr =&gt; arr.join(&quot;&quot;);</code></pre>
</blockquote>
<hr />
<h3 id="16-두-수-비교하기-문자열-조건-판단">16. 두 수 비교하기 (문자열 조건 판단)</h3>
<p><code>ineq</code>, <code>eq</code>, <code>n</code>, <code>m</code>이 주어졌을 때 주어진 비교 연산이 참이면 1, 아니면 0을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(ineq, eq, n, m) {
  return eval(`${n} ${ineq}${eq === &quot;!&quot; ? &quot;&quot; : eq} ${m}`) ? 1 : 0;
} // eval 함수로 문자열 연산 처리</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (ineq, eq, n, m) =&gt; eval(`${n} ${ineq}${eq === &quot;!&quot; ? &quot;&quot; : eq} ${m}`) ? 1 : 0;</code></pre>
</blockquote>
<hr />
<h3 id="17-홀짝에-따라-다른-값-반환하기">17. 홀짝에 따라 다른 값 반환하기</h3>
<p>양의 정수 <code>n</code>이 주어졌을 때, <code>n</code>이 홀수면 1부터 <code>n</code>까지의 모든 홀수의 합, 짝수면 짝수의 제곱의 합을 구하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(n) {
  if (n % 2 === 1) return ((n + 1) / 2) ** 2;
  return (n / 2) * (n / 2 + 1) * (2 * (n / 2) + 1) / 3;
} // 수학 공식 활용</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = n =&gt; n % 2 ? ((n + 1) / 2) ** 2 : (n / 2) * (n / 2 + 1) * (2 * (n / 2) + 1) / 3;</code></pre>
</blockquote>
<hr />
<h3 id="18-n의-배수">18. n의 배수</h3>
<p>자연수 <code>num</code>과 <code>n</code>이 주어졌을 때, <code>num</code>이 <code>n</code>의 배수이면 1, 아니면 0을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(num, n) {
  return num % n === 0 ? 1 : 0;
} // 기본 나머지 연산 활용</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (num, n) =&gt; +(num % n === 0);</code></pre>
</blockquote>
<hr />
<h3 id="19-더-크게-합치기">19. 더 크게 합치기</h3>
<p>두 수 <code>a</code>, <code>b</code>를 각각 문자열로 이어붙였을 때 두 경우 중 더 큰 수를 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(a, b) {
  return Math.max(Number(`${a}${b}`), Number(`${b}${a}`));
} // 문자열 변환 후 Math.max 비교</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (a, b) =&gt; Math.max(+(&quot;&quot; + a + b), +(&quot;&quot; + b + a));</code></pre>
</blockquote>
<hr />
<h3 id="20-문자-반복-출력하기">20. 문자 반복 출력하기</h3>
<p>문자열 <code>my_string</code>과 정수 <code>k</code>가 주어질 때, 각 문자를 <code>k</code>번 반복한 문자열을 반환하세요.</p>
<blockquote>
<pre><code class="language-js">function solution(my_string, k) {
  return [...my_string].map(ch =&gt; ch.repeat(k)).join(&quot;&quot;);
} // map과 repeat, join 조합</code></pre>
</blockquote>
<blockquote>
<pre><code class="language-js">const solution = (s, k) =&gt; [...s].map(c =&gt; c.repeat(k)).join(&quot;&quot;);</code></pre>
</blockquote>
<hr />