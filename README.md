<!doctype html>
<html lang="ko">
  <head>
    <meta charset="utf-8">
    <title>JavaScript</title>
    <style>
      * {
        box-sizing: border-box;
      }
      input {
        height: 40px;
        vertical-align: middle;
        border: 1px solid #dadada;
        padding: 0px 15px;
      }
    </style>
  </head>
  <body>
    <p>
      <input type="text" id="zip-code" placeholder="우편번호">
      <input type="button" onclick="execDaumPostcode()" value="우편번호 찾기">
    <p>
    </p>
      <input type="text" id="address-1" placeholder="도로명주소" style="width: 500px">
    <p>
    </p>
      <input type="text" id="address-2" placeholder="상세주소" style="width: 500px">
    </p>
    <script src="//t1.daumcdn.net/mapjsapi/bundle/postcode/prod/postcode.v2.js"></script>
    <script>
      function execDaumPostcode() {
        new daum.Postcode( {
          oncomplete: function( data ) {
            document.getElementById( 'zip-code' ).value = data.zonecode;
            document.getElementById( 'address-1' ).value = data.address;
          }
        } ).open();
      }
    </script>
  </body>
</html>
