<p><img alt="" src="https://velog.velcdn.com/images/ozen0718/post/bc84ae2e-9ec8-4cb1-be14-b72107d748b7/image.png" /></p>
<h1 id="day-1-drum-kit">Day 1: Drum Kit</h1>
<h2 id="최종-코드">최종 코드</h2>
<pre><code class="language-js">// 1. 모든 .key 요소를 한 번에 가져와 배열로 저장
const keys = Array.from(document.querySelectorAll(&quot;.key&quot;));

// 2. 키보드가 눌렸을 때 실행될 함수
const playSound = ({ keyCode }) =&gt; {
  // 눌린 키에 해당하는 audio와 div.key 요소 찾기
  const audio = document.querySelector(`audio[data-key=&quot;${keyCode}&quot;]`);
  const key = document.querySelector(`.key[data-key=&quot;${keyCode}&quot;]`);

  // 해당 키에 연결된 오디오가 없으면 종료
  if (!audio || !key) return;

  // 연타를 위한 audio 초기화
  audio.currentTime = 0;
  audio.play();

  // 버튼에 시각적 효과 클래스 추가
  key.classList.add(&quot;playing&quot;);
};

// 3. CSS transition 애니메이션이 끝났을 때 실행될 함수
const removeTransition = ({ propertyName, target }) =&gt; {
  // transform이 아닌 속성 변화는 무시 (예: border-color 등)
  if (propertyName !== &quot;transform&quot;) return;

  // 애니메이션 효과 제거
  target.classList.remove(&quot;playing&quot;);
};

// 4. 각 키 버튼마다 transitionend 이벤트 연결
keys.forEach((key) =&gt;
  key.addEventListener(&quot;transitionend&quot;, removeTransition)
);

// 5. 전체 문서에 keydown 이벤트 연결
window.addEventListener(&quot;keydown&quot;, playSound);</code></pre>
<hr />
<h3 id="정리">정리</h3>
<h3 id="data-key-속성">data-key 속성</h3>
<ul>
<li>HTML에서 커스텀 속성을 정의할 때 사용하는 표준 방법</li>
<li><code>data-key</code>는 JavaScript에서 키보드 코드와 DOM 요소를 연결하기 위해 사용됨</li>
</ul>
<h4 id="예시">예시</h4>
<pre><code class="language-html">&lt;div class=&quot;key&quot; data-key=&quot;65&quot;&gt;A&lt;/div&gt;
&lt;audio data-key=&quot;65&quot; src=&quot;sounds/clap.wav&quot;&gt;&lt;/audio&gt;</code></pre>
<ul>
<li>JavaScript에서는 다음과 같이 선택할 수 있음:</li>
</ul>
<pre><code class="language-js">document.querySelector(`audio[data-key=&quot;${keyCode}&quot;]`)</code></pre>
<p> <code>keyCode</code> 값에 따라 HTML 요소를 동적으로 선택할 수 있는 구조가 만들어짐</p>
<hr />
<h3 id="keydown-이벤트">keydown 이벤트</h3>
<ul>
<li>사용자가 키보드를 <strong>누를 때</strong> 발생하는 이벤트</li>
<li>눌린 키에 대한 정보를 담은 이벤트 객체가 자동 전달됨</li>
</ul>
<pre><code class="language-js">window.addEventListener(&quot;keydown&quot;, playSound);</code></pre>
<p> <code>keydown</code>은 키가 눌릴 때 즉시 발생하며, <code>e.keyCode</code>로 어떤 키인지 확인 가능</p>
<hr />
<h3 id="eventkeycode">event.keyCode</h3>
<ul>
<li><p>키보드 입력 시 눌린 키를 ASCII 기반 숫자로 반환</p>
</li>
<li><p>예:</p>
<ul>
<li>A: <code>65</code></li>
<li>S: <code>83</code></li>
<li>D: <code>68</code></li>
</ul>
<p><a href="https://keycode.info">keycode.info</a> 에서 키 눌러보면 keyCode 확인 가능  </p>
<blockquote>
<p>최신 브라우저에서는 <code>e.code</code> 사용 권장</p>
</blockquote>
</li>
</ul>
<hr />
<h3 id="audiocurrenttime--0">audio.currentTime = 0</h3>
<ul>
<li>오디오를 매번 <strong>처음부터 재생하기 위해 필요한 코드</strong></li>
</ul>
<pre><code class="language-js">audio.currentTime = 0;
audio.play();</code></pre>
<ul>
<li><p>이걸 쓰지 않으면, 이미 재생 중인 오디오는 반복 재생되지 않음</p>
</li>
<li><p>키를 빠르게 연타할 때 <strong>소리가 반복 재생되게 하려면 반드시 필요함</strong></p>
<p><code>currentTime = 0</code>은 오디오의 재생 지점을 강제로 처음으로 돌리는 역할</p>
</li>
</ul>
<hr />
<h3 id="queryselector">querySelector()</h3>
<ul>
<li>CSS 선택자와 일치하는 <strong>첫 번째 요소만 반환</strong></li>
<li><code>data-key</code> 등으로 조건부 요소 선택 가능</li>
</ul>
<pre><code class="language-js">document.querySelector(`.key[data-key=&quot;${keyCode}&quot;]`);</code></pre>
<p> <code>querySelectorAll()</code>과 달리, 하나만 반환하므로 반복이 필요하면 Array로 변환 필요</p>
<hr />
<h3 id="transitionend-이벤트">transitionend 이벤트</h3>
<ul>
<li>CSS <code>transition</code>이 끝났을 때 발생하는 이벤트</li>
<li>요소에 적용된 스타일 애니메이션이 완료되었음을 알 수 있음</li>
</ul>
<pre><code class="language-js">const removeTransition = (e) =&gt; {
  if (e.propertyName !== &quot;transform&quot;) return;
  e.target.classList.remove(&quot;playing&quot;);
};</code></pre>
<p> <code>propertyName</code> 필터는 <code>transform</code> 속성에 대해서만 반응하게 하기 위한 조건</p>
<hr />
<h3 id="playing-클래스">.playing 클래스</h3>
<ul>
<li>키를 눌렀을 때 버튼에 시각적인 눌림 효과를 주는 클래스</li>
</ul>
<pre><code class="language-css">.playing {
  transform: scale(1.1);
  border-color: #ffc600;
  box-shadow: 0 0 10px #ffc600;
}</code></pre>
<ul>
<li>JavaScript에서는 아래처럼 추가/제거</li>
</ul>
<pre><code class="language-js">key.classList.add(&quot;playing&quot;);        // 눌렸을 때 추가
e.target.classList.remove(&quot;playing&quot;); // 효과 종료 후 제거</code></pre>
<p> 클래스 추가 → 애니메이션 시작<br />클래스 제거 → 다시 원상복구</p>