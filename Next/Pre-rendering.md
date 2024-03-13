## Pre-rendering
NextJS는 모든 페이지를 pre-render 한다. 이 pre-render한다는 의미는 모든 페이지를 위한 HTML을 Client사이드에서 자바스크립트로 처리하기 전 "사전에" 생성한다는 것이다. 이렇게 하기에 SEO 검색엔진 최적화가 좋아진다
<br><br>
각각 생성된 HTML페이지는 최소한의 자바스크립트와 연관되어있는데, Client Side에서는 브라우저에 페이지가 로드되었을 때, 자바스크립트가 페이지를 완전히 완성시킨다. 이 과정을 <b>hydration</b>이라고 한다.

> <b>hydration</b>: 페이지가 브라우저에 로드되고 자바스크립트 코드가 실행되면서 페이지가 인터렉티브 하게 동작하는 상태가 되는 과정

![Using Next.js](https://user-images.githubusercontent.com/63354527/176647877-68aeef19-420b-4d28-a12d-58ba73894c2c.png)

Pre-rendering 방식은 HTML 파일을 통해 정적인 화면을 먼저 보여준다. 이후 JS 파일을 로드해와서 화면에서의 클릭 등의 이벤트 처리가 이뤄질 수 있도록 연결한다. 

화면은 먼저 보이지만, 반응 할 수 있는 시점까지 다소 시간이 걸릴 수 있다. 이를 TTI와 TTV가 다르다(TTI !== TTV)라고 한다.

TTI(Time To Interact): 페이지가 로드되고 자바스크립트 코드가 실행되면서 페이지가 인터렉티브 하게 동작하는 걸리는 시간을 의미한다. (사용자와 상호작용 가능할 때까지의 시간)

TTV(Time To View): 페이지가 사용자에게 보여지는데까지 걸리는 시간.

Next.js의 pre-rendering 형태는 Static Generation과 Server Side Rendering으로 나뉘며 각 페이지별로 다르게 적용할 수 있다. 이 pre-rendering 방식의 차이는 HTML을 생성할 때에 있다.

pre-render가 필요없는 페이지는(SEO 필요없는 페이지) CSR로 처리하면 된다.  컨텐츠가 빈번하게 바뀐다면 CSR로 처리하는 것이 성능상 더욱 좋다.
