# **React Router Dom**

> **Router**
```javascript
import { BrowerRouterm Route, Routes} from 'react-router-dom';
```
- BrowserRouter
  - React 라우터의 도움을 받고 싶은 컴포넌트의 최상위 컴포넌트를 감싸는 래퍼 컴포넌트
  
  
**페이지 경로 이동은 이런식으로 작성해주면 된다**
```javascript
<Routes>
  <Route path=""> element={<Home />} />
<Routes>
```
* **NotFound 경로 설정**
```javascript
<Route path="*"> element={'Not Found'} />
```


## **Link**
- 단일 페이지 어플리케이션을 만들 때 중요한 점은 페이지가 리로드 되지 않고 동적으로 가져오는 데이터는 코드를 작성해서 만들거나 Ajax 같은 기술을 이용해 비동기적으로 데이터를 가져와서 페이지를 제작하는 것 
## **NavLink**
- NavLink를 사용하면 class="active"라는 속성이 생긴다. 
- 자신이 어떤 페이지에 위치하고 있는 지 직관적으로 알 수 있는 장점이 생김 

