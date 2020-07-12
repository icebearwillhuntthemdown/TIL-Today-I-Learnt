# Legacy Code
개발자 채용 공고를 훑다 보면 레거시 코드라는 용어를 자주 접할 수 있다. Legacy 자체는 유산, 과거의 산물을 의미하는데 Legecy Code는 구체적으로 뭘까?  

### Definition?  
[여기](https://www.perforce.com/blog/qac/8-tips-working-legacy-code)에서는 레거시 코드를 이렇게 정의한다.
> Legacy code is **any code that is maintained by someone who didn't write it**. However, it can also be **any code that you don't understand and that's difficult to change**. This can refer to code inherited from someone else, or to code inherited from an earlier version of the software, or to code without unit tests.

[여기](https://understandlegacycode.com/blog/what-is-legacy-code-is-it-code-without-tests/)의 정의는 이렇다.
> Legacy code is **valuable code you're afraid to change**. You want to chage the code, but you have a hard time doing so because you don't know how not to break existing behavior. This is Legacy Code.  

Mighty Google에게 물어봤더니 의외로 정의가 다양하다. 첫사랑의 정의마냥, 각자 자신의 경험에 기반해 다른 정의를 내리고 있었다. 하지만 그 모든 정의를 관통하는 개념은 있었다. 바로 '유지보수가 어려운 과거의 코드'라는 점이다.

### How to work with Legacy Code?
참조한 글들을 종합해보면, 적절한 테스트를 하지 않아서든, 다른 개발자가 쓴 (형편없는) 코드여서든, 레거시 코드는 분명 가치있지만 건드리기 힘든 코드다. 하지만 아예 백지에서 다시 시작하지 않는 이상 레거시 코드를 피할 수는 없다. [여기](https://www.perforce.com/blog/qac/8-tips-working-legacy-code) 정리된 레거시 코드를 다루는 팁 8가지는 읽어봄직하다. 아래는 일부 발췌. 
> 1.Test the code : This will help you understand what the code actually does. Once you understand the code, you can make changes with greater confidence.  
> 3.Only rewrite code when it's necessary : It takes too much time and too many programmers to rewrite everything. And even if you do it, rewriting code can introduce new bugs, or it can remove hidden functionality.  
> 4.Try Refactoring instead : Refactor code that has unit tests so you know what you have and test after refactoring to make sure you didn't break anything.  

### Legacy Code is a personal point of view
> It depends on your understanding of the code. And your feeling about changing it.  

[이 글](https://understandlegacycode.com/blog/what-is-legacy-code-is-it-code-without-tests/)에서 가장 인상 깊은 부분이다. 레거시 코드는 으레 지저분한 코드, 이해하기 어려운 코드 등 부정적으로 여겨지지만, 사실 개인의 관점에 따라 달라질 수 있는 생각이라는 것.  

그저 레거시 코드가 정확히 뭔지 궁금해서 찾아보기 시작했는데 레거시 코드, 테스트, 리팩토링을 왜 다들 그렇게 강조하는지 알게된 시간이었다. 내가 작성한 코드를 레거시 코드로 마주할 사람을 생각해서라도 클린 코드를 쓰려고 노력해야겠다.  




