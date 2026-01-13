# Vue Directive / Props 정리

---

## v-on

- v-on:click=""
- v-on == @

---

## v-show

- v-show=""
- 사용하게 되면, component는 dom 내에서 보이고 가려짐
- 자주 이뤄지는 이벤트에 사용하기 좋음

---

## v-if / v-else-if / v-else

- v-if/else if/else=""
- 사용하게 되면, component는 dom에서 아예 빠졌다가 다시 삽입됨
- 간혹 사용되는 이벤트에 사용하기 좋음
- takes more resource

---

## v-bind

- v-bind:x=""
- v-bind == :

---

## prop

- prop: 부모 -> 자식으로 값을 넘겨주는 것

---

## emit

- 자식에서 $emit('아무이름')을 지정
- 부모에서 @아무이름="자식에서 실행하고 싶은 부모 function이름"을 전달
- 자식에서 사용가능

---

# 모바일에서 Vue 개발 서버 접속

---

## 1. 현재 PC의 IP 주소 확인

- Window 인 경우
    - cmd에: ipconfig

---

## 2. Vue 개발 서버 실행 후 모바일에서 접속

- network 주소를 직접 모바일에 쳐서 접속
    - ex. http://192.168.xxx.xxx:xxxx

- Vue 개발 서버 실행 명령어

    - npm run serve -- --host 0.0.0.0
