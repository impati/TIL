## Spring Web Exception 은 어디서 처리할까 ? 
별도의 ExceptionHandler 로 예외를 처리하지 않는 이상 `DefaultHandlerExceptionResolver` 가 동작한다.
Spring Web 이 제공하는 예외 중 커스텀하게 처리하고 싶은 경우 `ResponseEntityExceptionHandler` 를 상속받고 Override 해주면 가능하다.
혹은 Spring Web Exception 을 직접 `@ExceptionHandler(HttpRequestMethodNotSupportedException.class)` 로 처리해주는 방법도 있다.

## 대표적인 Spring Web 예외들

1. `HttpRequestMethodNotSupportedException`: 지원되지 않는 HTTP 요청 메서드를 사용하여 요청한 경우 발생하는 예외입니다.

2. `HttpMediaTypeNotSupportedException`: 지원되지 않는 미디어 타입을 사용하여 요청한 경우 발생하는 예외입니다. 요청 본문의 Content-Type이 서버가 처리할 수 없는 형식일 때 발생합니다.

3. `HttpMediaTypeNotAcceptableException`: 서버가 클라이언트의 Accept 헤더에 명시된 미디어 타입으로 응답을 제공할 수 없는 경우 발생하는 예외입니다.

4. `MissingPathVariableException`: 경로 변수가 누락된 경우 발생하는 예외입니다. 예를 들어, @PathVariable로 선언된 경로 변수에 해당하는 값이 없을 때 발생합니다.

5. `MissingServletRequestParameterException`: 필수 요청 파라미터가 누락된 경우 발생하는 예외입니다. 예를 들어, 쿼리 파라미터나 폼 데이터에 필요한 파라미터가 전달되지 않았을 때 발생합니다.

6. `ServletRequestBindingException`: 요청 바인딩과 관련된 문제가 발생했을 때 발생하는 예외입니다.

7. `ConversionNotSupportedException`: 데이터 타입 변환을 할 수 없는 경우 발생하는 예외입니다.

8. `TypeMismatchException`: 데이터 타입이 예상과 다른 경우 발생하는 예외입니다. 예를 들어, 숫자 타입으로 변환할 수 없는 문자열이 전달되는 경우 발생할 수 있습니다.

9. `HttpMessageNotReadableException`: HTTP 메시지를 읽을 수 없는 경우 발생하는 예외입니다. 주로 요청 본문의 JSON 또는 XML과 같은 형식이 잘못된 경우 발생합니다.

10. `HttpMessageNotWritableException`: HTTP 메시지를 쓸 수 없는 경우 발생하는 예외입니다. 주로 응답 본문을 생성하는 데 문제가 발생했을 때 발생합니다.

11. `MethodArgumentNotValidException`: @Valid 어노테이션을 사용하여 유효성 검사가 실패한 경우 발생하는 예외입니다. 주로 요청 데이터의 유효성 검사를 처리할 때 발생합니다.

12. `MissingServletRequestPartException`: Multipart 요청에서 필수 파일 또는 파트가 누락된 경우 발생하는 예외입니다.

13. `BindException`: 데이터 바인딩에 실패했을 때 발생하는 예외입니다.

14. `NoHandlerFoundException`: 요청에 해당하는 핸들러(컨트롤러)를 찾지 못했을 때 발생하는 예외입니다. 주로 404 에러 처리에 사용됩니다.

15. `AsyncRequestTimeoutException`: 비동기 요청 처리 시간이 초과되었을 때 발생하는 예외입니다. 주로 비동기 요청의 타임아웃 처리에 사용됩니다.
