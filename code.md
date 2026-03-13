```js
chatInput.addEventListener('input', () => {
    chatInput.sytle.height = 'auto';
    chatInput.style.height = Math.min(chatInput.scrollheight, 200) + 'px'; 
});

```

`chatInput.sytle.height = 'auto';`  
- 현재 적용된 높이를 초기화
- `scrollHeight`를 정확한 값으로 재계산하기 위함

`Math.min(chatInput.scrollHeight, 200);`  
- `scrollHeight` : 내용물 전체 높이(스크롤 포함)
- `200` : 최대 높이 제한(max-height)
- `Math.min()` : 둘 중 작은 값 선택


**동작 원리**  

1. 내용이 적을 때: scrollHeight: 30px -> Math.min(30, 200) = 30px
2. 내용이 많을 때: scrollHeight: 150px -> Math.min(150, 200) = 150px
3. 내용이 매우 많을 때: scrollheight: 300px -> Math.min(300, 200) => 200px(최대치 유지) 

**결과**  
- 입력 내용에 따라 높이가 자동 조절
- 200px 이상은 증가하지 않음(스크롤 가능)