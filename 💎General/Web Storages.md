# Storage

## Cookies
1. 웹 서버가 HTTP response header의 `set-cookie`에 데이터를 넣어 전달하면 브라우저에 저장
    + e.g.) session identifier
2. 브라우저는 쿠키의 내용을 request header에 넣어서 전달 
    - session identifier
3. 서버는 request header의 session identifier를 읽어 사용자 식별

### syntax
`document.cookie = "name=value"; "user=John"; path=/; expires=Tue, 19 Jan 2038 03:14:07 GMT`
- "name=value" pair
- `;` separator
- encoding required : encodeURIComponent(name), encodeURIComponent(value) 

### lifecycle
해당 값이 유효한 동안은 브라우저를 닫아도 사라지지 않음
- `expires` : 유효일자. `expires=Tue, 19 Jan 2038 03:14:07 GMT`
- `max-age` : 만료기간. `max-age=3600`
- session cookie : expires(유효일자), max-age(만료기간)이 지정돼 있지 않으면 세션처럼 페이지가 닫힐 때 쿠키가 사라짐.

## Web Storages 
- `sessionStorage`
- `localStorage`
- cookie와 달리 web storage object는 서버로 전송되지 않음

### Props
- setItem(k, v)
- getItem(k)
- removeItem(k)
- clear()
- key(index) : returns the key of given index
- length
```typescript
// store data
localStorage.userName = "개개"    // bad practice
localStorage.setItem("favourite film", "Suspiria")

// remove data
localStorage.removeItem("userName")
localStorage.removeItem("favourite film")
```

### SessionStorage
    + page 
    - page session lasts as long as the browser is open, and survives over page reloads and restores.
    - opening a page in a new tab or window creates a new session
    - opening multiple tabs/windows with the same URL creates `sessionStorage` for each.
    - closing a tab/window ends the session and clears objects in `sessionStorage`

### Local Strogae
    + browser's storage
    - 오리진(domain/port/protocol)만 같으면 url이 달라도 데이터가 공유된다.
    - 브라우저나 OS가 재시작하더라도 데이터가 파기되지 않는다.
    - the stored data is saved across browser sessions.
    - `localStorage` and `sessionStorage` are works exactly the same except 
    `localStorage` has no expiration time, unlike `sessionStorage`. (unless the data is stored in incognito sessions.)
    - Data in local storage lasts until it is explicitly removed.

### Storage Events
A storage event is called when `localStorage` or `sessionStorage` changes, like when `setItem()` or `removeItem()` or `clear()` is called.

#### Props
- key : the key of changed data
- oldValue : previous value
- newValue : changed, current value
- url : the url to where the change happened
- storageArea : the `sessionStorage` or `localStorage` object that has been chaged.

```typescript
window.onstorage = event => {
    if(event.key != 'now') return;
    alert(event.key + ':' + event.newValue + at + event.url)
}

localStorage.setItem('now', Data.now());
```
#### +)Protocol Dependent
Data stored in `sessionStorage` and `localStorage` is specific to the protocol of the page. For instance, data accessed with HTTP is put in a different storage from the same site accessed with HTTPS.

## References
- [cookie](https://ko.javascript.info/cookie)
- [Please Stop Using Local Storage
 ](https://www.rdegges.com/2018/please-stop-using-local-storage/)
- [localStorage와 sessionStorage](https://ko.javascript.info/localstorage) 
