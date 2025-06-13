<h3 id="1-주사위-게임-2">1. 주사위 게임 2</h3>
<p><strong>문제 요약</strong><br />세 사람의 주사위 값이 주어졌을 때, 같은 수가 3개면 10,000 + (같은 수) × 1,000<br />같은 수가 2개면 1,000 + (같은 수) × 100<br />모두 다르면 가장 큰 수 × 100<br />해당 규칙을 따라 상금을 계산하는 함수를 작성하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(a, b, c) {
  if (a === b &amp;&amp; b === c) return 10000 + a * 1000; // 세 숫자가 모두 같을 경우
  if (a === b || a === c) return 1000 + a * 100;   // a가 b나 c와 같을 경우
  if (b === c) return 1000 + b * 100;              // b와 c가 같을 경우
  return Math.max(a, b, c) * 100;                  // 모두 다르면 가장 큰 수 * 100
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>if (a === b &amp;&amp; b === c)</code> : 세 수가 모두 같을 때 최우선으로 처리합니다.</li>
<li><code>if (a === b || a === c)</code> : <code>a</code>가 <code>b</code> 또는 <code>c</code>와 같으면, 두 수가 같다고 판단합니다.</li>
<li><code>if (b === c)</code> : 앞에서 <code>a === b</code>, <code>a === c</code>를 확인했기 때문에 여기선 <code>b === c</code>만 확인.</li>
<li><code>Math.max(a, b, c)</code> : 세 수가 모두 다르면 가장 큰 값을 찾아 100을 곱합니다.</li>
</ul>
<hr />
<h3 id="2-원소들의-곱과-합">2. 원소들의 곱과 합</h3>
<p><strong>문제 요약</strong><br />정수 배열 <code>num_list</code>가 주어질 때, 모든 원소의 곱이 모든 원소의 합의 제곱보다 작으면 1, 아니면 0을 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(num_list) {
  const sum = num_list.reduce((a, b) =&gt; a + b);   // 합
  const product = num_list.reduce((a, b) =&gt; a * b); // 곱
  return product &lt; sum * sum ? 1 : 0;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>reduce((a, b) =&gt; a + b)</code>는 배열의 모든 수를 더합니다.</li>
<li><code>reduce((a, b) =&gt; a * b)</code>는 배열의 모든 수를 곱합니다.</li>
<li>합의 제곱이 곱보다 큰지 비교해 1 또는 0을 반환합니다.</li>
</ul>
<hr />
<h3 id="3-이어-붙인-수">3. 이어 붙인 수</h3>
<p><strong>문제 요약</strong><br />정수 배열 <code>num_list</code>가 주어졌을 때, 짝수는 따로 이어 붙이고 홀수도 따로 이어 붙인 뒤 정수로 만들어 합을 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(num_list) {
  let even = '';
  let odd = '';
  num_list.forEach(n =&gt; n % 2 === 0 ? even += n : odd += n);
  return +even + +odd;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>짝수/홀수로 나눠 각각 문자열로 이어 붙입니다.</li>
<li><code>+even</code>, <code>+odd</code>는 문자열을 정수로 변환합니다.</li>
<li>최종적으로 두 수를 더해 반환합니다.</li>
</ul>
<hr />
<h3 id="4-마지막-두-원소">4. 마지막 두 원소</h3>
<p><strong>문제 요약</strong><br />배열의 마지막 원소가 그 앞 원소보다 크면 두 수의 차를 추가, 작으면 두 배를 추가한 배열을 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(num_list) {
  const len = num_list.length;
  const last = num_list[len - 1];
  const prev = num_list[len - 2];
  num_list.push(last &gt; prev ? last - prev : last * 2);
  return num_list;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>배열의 마지막 원소(<code>last</code>)와 그 이전 원소(<code>prev</code>)를 가져옵니다.</li>
<li>조건에 따라 계산된 값을 배열에 추가합니다.</li>
</ul>
<hr />
<h3 id="5-수-조작하기-1">5. 수 조작하기 1</h3>
<p><strong>문제 요약</strong><br />정수 <code>n</code>과 문자열 <code>control</code>이 주어졌을 때, control에 따라 <code>n</code>을 조작하세요.<br />('w': +1, 's': -1, 'd': +10, 'a': -10)</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(n, control) {
  for (let c of control) {
    if (c === 'w') n += 1;
    else if (c === 's') n -= 1;
    else if (c === 'd') n += 10;
    else if (c === 'a') n -= 10;
  }
  return n;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>문자열을 하나씩 순회하며 해당 조건에 따라 값을 더하거나 뺍니다.</li>
<li><code>for...of</code> 구문은 문자열을 반복할 때 유용합니다.</li>
</ul>
<hr />
<h3 id="6-수-조작하기-1">6. 수 조작하기 1</h3>
<p><strong>문제 요약</strong><br />문자열 <code>control</code>에 따라 숫자 <code>n</code>을 조작합니다.  </p>
<ul>
<li>&quot;w&quot;: +1</li>
<li>&quot;s&quot;: -1</li>
<li>&quot;d&quot;: +10</li>
<li>&quot;a&quot;: -10<br />각 문자를 순회하며 명령을 수행한 결과를 반환합니다.</li>
</ul>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(n, control) {
  for (let ch of control) {
    if (ch === &quot;w&quot;) n += 1;
    else if (ch === &quot;s&quot;) n -= 1;
    else if (ch === &quot;d&quot;) n += 10;
    else if (ch === &quot;a&quot;) n -= 10;
  }
  return n;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>각 문자를 반복문으로 돌며 해당하는 명령에 따라 값을 조작합니다.</li>
<li>명령 문자열을 switch 문으로 바꿔도 됩니다.</li>
</ul>
<hr />
<h3 id="7-수-조작하기-2">7. 수 조작하기 2</h3>
<p><strong>문제 요약</strong><br />정수 배열 <code>numLog</code>가 주어졌을 때, 앞뒤 숫자의 차이를 기준으로 어떤 조작이 있었는지 문자열로 복원하세요.<br />규칙: +1 → &quot;w&quot;, -1 → &quot;s&quot;, +10 → &quot;d&quot;, -10 → &quot;a&quot;</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(numLog) {
  let answer = &quot;&quot;;
  for (let i = 1; i &lt; numLog.length; i++) {
    const diff = numLog[i] - numLog[i - 1];
    if (diff === 1) answer += &quot;w&quot;;
    else if (diff === -1) answer += &quot;s&quot;;
    else if (diff === 10) answer += &quot;d&quot;;
    else if (diff === -10) answer += &quot;a&quot;;
  }
  return answer;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>연속된 두 수의 차이를 기준으로 조작 문자열을 복원합니다.</li>
<li>명령어를 조건문으로 분기하여 추가합니다.</li>
</ul>
<hr />
<h3 id="8-수열과-구간-쿼리-3">8. 수열과 구간 쿼리 3</h3>
<p><strong>문제 요약</strong><br />배열과 쿼리 [i, j]가 주어졌을 때, 각 쿼리마다 i번째와 j번째 값을 바꿉니다.<br />모든 쿼리 반영 후 배열을 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(arr, queries) {
  for (const [i, j] of queries) {
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
  return arr;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>구조 분해 할당 문법을 이용해 간단하게 두 값을 스왑할 수 있습니다.</li>
</ul>
<hr />
<h3 id="9-수열과-구간-쿼리-2">9. 수열과 구간 쿼리 2</h3>
<p><strong>문제 요약</strong><br />배열과 쿼리 [s, e, k]가 주어졌을 때, s~e 범위 중 k보다 크면서 가장 작은 값을 찾아 배열에 담아 반환하세요.<br />해당 값이 없으면 -1을 반환합니다.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(arr, queries) {
  return queries.map(([s, e, k]) =&gt; {
    const filtered = arr.slice(s, e + 1).filter(v =&gt; v &gt; k);
    return filtered.length ? Math.min(...filtered) : -1;
  });
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>구간을 잘라내고 <code>k</code>보다 큰 값만 필터링</li>
<li><code>Math.min(...arr)</code>로 최소값 추출</li>
</ul>
<hr />
<h3 id="10-수열과-구간-쿼리-4">10. 수열과 구간 쿼리 4</h3>
<p><strong>문제 요약</strong><br />배열과 쿼리 [s, e, k]가 주어졌을 때, 인덱스가 k로 나눠떨어지는 위치의 값만 +1 증가시키는 작업을 합니다.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(arr, queries) {
  for (const [s, e, k] of queries) {
    for (let i = s; i &lt;= e; i++) {
      if (i % k === 0) arr[i]++;
    }
  }
  return arr;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>i % k === 0</code> 조건으로 해당 인덱스를 선택</li>
<li>반복문 안에서 직접 배열 값을 조작합니다.</li>
</ul>
<hr />
<h3 id="11-카운트-업">11. 카운트 업</h3>
<p><strong>문제 요약</strong><br /><code>start_num</code>부터 <code>end_num</code>까지의 모든 정수를 오름차순으로 담은 배열을 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(start, end) {
  return Array.from({ length: end - start + 1 }, (_, i) =&gt; start + i);
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>Array.from()</code>은 배열을 만들 때 사용됩니다.</li>
<li><code>length: end - start + 1</code>로 필요한 길이만큼 배열을 생성합니다.</li>
<li><code>(_, i) =&gt; start + i</code>는 각 인덱스에 대해 값을 <code>start + i</code>로 생성합니다.</li>
</ul>
<hr />
<h3 id="12-콜라츠-수열-만들기">12. 콜라츠 수열 만들기</h3>
<p><strong>문제 요약</strong><br />정수 <code>n</code>이 주어질 때, 콜라츠 수열을 배열로 반환하세요.  </p>
<ul>
<li>짝수면 2로 나누고, 홀수면 3을 곱하고 1을 더함.  </li>
<li>1이 될 때까지 반복.</li>
</ul>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(n) {
  const result = [];
  while (true) {
    result.push(n);
    if (n === 1) break;
    n = n % 2 === 0 ? n / 2 : 3 * n + 1;
  }
  return result;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>while (true)</code> 반복문 안에서 조건에 따라 수를 계속 변환하며 <code>result</code>에 저장합니다.</li>
<li>짝수는 <code>/2</code>, 홀수는 <code>3n+1</code> 규칙을 사용합니다.</li>
<li><code>n === 1</code>일 때 반복문을 종료합니다.</li>
</ul>
<hr />
<h3 id="13-배열-만들기-4">13. 배열 만들기 4</h3>
<p><strong>문제 요약</strong><br /><code>arr</code>이 주어졌을 때 특정 규칙에 따라 새로운 배열을 만들어 반환하세요.  </p>
<ul>
<li>빈 배열 <code>stk</code>에 대해  <ul>
<li><code>i</code>가 배열 범위 내고  <ul>
<li><code>stk</code>이 비었거나 <code>stk[stk.length - 1] &lt; arr[i]</code>이면 <code>stk</code>에 <code>arr[i]</code> 추가  </li>
<li>아니면 <code>stk.pop()</code></li>
</ul>
</li>
</ul>
</li>
</ul>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(arr) {
  const stk = [];
  let i = 0;
  while (i &lt; arr.length) {
    if (stk.length === 0 || stk.at(-1) &lt; arr[i]) {
      stk.push(arr[i]);
      i++;
    } else {
      stk.pop();
    }
  }
  return stk;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>스택 문제의 기본 방식.</li>
<li><code>stk.at(-1)</code>는 스택의 마지막 원소를 참조합니다.</li>
<li>조건에 따라 push 또는 pop하고 <code>i</code>의 증가 여부가 결정됩니다.</li>
</ul>
<hr />
<h3 id="14-간단한-논리-연산">14. 간단한 논리 연산</h3>
<p><strong>문제 요약</strong><br />정수 <code>x</code>, <code>y</code>, <code>z</code>가 주어질 때 <code>(x &lt; y)</code>와 <code>z</code> 사이의 논리 연산 결과를 반환하세요.  </p>
<ul>
<li><code>boolean x</code>, <code>boolean y</code>, <code>boolean z</code>는 0 또는 1로 주어집니다.</li>
</ul>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(x1, x2, x3, x4) {
  return (x1 || x2) &amp;&amp; (x3 || x4);
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>문제는 OR, AND 연산자 이해 문제입니다.</li>
<li><code>||</code>는 OR, <code>&amp;&amp;</code>는 AND로 사용됩니다.</li>
<li>괄호 우선순위에 따라 <code>(x1 OR x2) AND (x3 OR x4)</code> 계산합니다.</li>
</ul>
<hr />
<h3 id="15-주사위-게임-3">15. 주사위 게임 3</h3>
<p><strong>문제 요약</strong><br />세 정수 <code>a</code>, <code>b</code>, <code>c</code>가 주어졌을 때,  </p>
<ul>
<li>모두 같으면 <code>(a + b + c) * (a^2 + b^2 + c^2) * (a^3 + b^3 + c^3)</code></li>
<li>두 개 같으면 <code>(a + b + c) * (a^2 + b^2 + c^2)</code></li>
<li>모두 다르면 <code>a + b + c</code></li>
</ul>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(a, b, c) {
  const sum = a + b + c;
  const squareSum = a ** 2 + b ** 2 + c ** 2;
  const cubeSum = a ** 3 + b ** 3 + c ** 3;

  if (a === b &amp;&amp; b === c) return sum * squareSum * cubeSum;
  if (a === b || b === c || a === c) return sum * squareSum;
  return sum;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li>조건문 순서에 따라 가장 복잡한 조건부터 체크.</li>
<li>제곱, 세제곱은 <code>**</code> 연산자 사용.</li>
<li>간단한 조건 분기 + 수식 계산 문제입니다.</li>
</ul>
<hr />
<h3 id="16-9로-나눈-나머지">16. 9로 나눈 나머지</h3>
<p><strong>문제 요약</strong><br />주어진 숫자 문자열에서 모든 자리수를 더한 후, 9로 나눈 나머지를 반환하세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(number) {
  return [...number].reduce((acc, cur) =&gt; acc + Number(cur), 0) % 9;
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>[...]</code> : 문자열을 문자 배열로 변환.</li>
<li><code>reduce</code> : 각 자리수를 숫자로 바꿔 모두 더함.</li>
<li><code>% 9</code> : 9로 나눈 나머지를 반환.</li>
</ul>
<hr />
<h3 id="17-문자열-여러-번-뒤집기">17. 문자열 여러 번 뒤집기</h3>
<p><strong>문제 요약</strong><br />문자열과 [s, e] 범위가 담긴 2차원 배열 <code>queries</code>가 주어질 때, 해당 구간만큼 반복적으로 문자열을 뒤집으세요.</p>
<hr />
<p><strong>정답 코드</strong></p>
<pre><code class="language-js">function solution(my_string, queries) {
  let str = [...my_string];
  for (const [s, e] of queries) {
    const reversed = str.slice(s, e + 1).reverse();
    str.splice(s, e - s + 1, ...reversed);
  }
  return str.join('');
}</code></pre>
<hr />
<p><strong>해설</strong></p>
<ul>
<li><code>slice(s, e + 1)</code> : s~e 구간 자름</li>
<li><code>reverse()</code> : 해당 구간 뒤집기</li>
<li><code>splice</code> : 원본 배열에 뒤집은 배열 삽입</li>
<li><code>join('')</code> : 배열을 다시 문자열로 변환</li>
</ul>