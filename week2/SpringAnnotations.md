## 학습 키워드

- @RequestMapping
  - @GetMapping
  - @PostMapping
  - @PatchMapping
  - @DeleteMapping
  - @PathVariable
- @RequestBody
- @ExceptionHandler
- @ResponseStatus

## @RequestMapping

- 매핑된 URL이 호출되면 해당 메서드를 실행한다.
- Method를 지정해주지 않으면 매핑된 URL에 대한 모든 방식의 Http Method방식을 처리하게 된다.
- Method를 별도로 지정 해줄수 있다 ex) method = RequestMethod.GET

### @GetMapping

- Get방식의 요청을 처리한다
- 요청에 Body가 없기에 주로 헤더에 있는 값과 쿼리스트링을 사용해 응답을 한다.

* 주로 조회에 사용

### @PostMapping

- Post방식의 요청을 처리

* 요청의 Body에 데이터를 담아 받은 후 응답할때 사용하는 애너테이션

- 주로 생성에 사용

### @PatchMapping

- Patch방식의 요청을 처리한다.

* 요청의 Body에 데이터를 담아 받은 후 리소스의 일부를 업데이트한다
* 리소스를 일부수정하기 때문에 변경하지 않는 데이터를 보내지 않아도 Put처럼 Null값이 들어가지 않는다.
* Put은 덮어 쓰는 개념이여서 일부 값만 요청에 담아 보낼 경우 값이 입력되지 않은 값들은 Null로 들어가게된다.

### @DeleteMapping

- Delete방식의 요청을 처리한다
- 주로 데이터를 삭제 할 때 사용한다.

### @PathVariable

- 매핑된 URL에 /{}로 들어가는 패스 변수를 받는다
- 메서드의 매개 변수에 사용하게되면 URL에 있는 {}의 값을 매개변수로 받아 오게 된다.

```
URL Get /users/1

@GetMapping("/users/{id})
public UserResponseDto findById(@PathVariable Long id){

}
```

## @RequestBody

- 해당 애너테이션이 붙은 파라미터는 http의 요청의 body가 그대로 전달된다

```
URL PATCH /usuers/1
{
    "name": "Mike"
}

@PatchMapping("/users/{id}")
public UserResponseDto updateById(@RequestBody UserRequestDto userRequestDto){

}

```

## @ExceptionHandler

- 해당 애노테이션이 붙어 있는 메소드는 ()안에 있는 클래스 타입의 예외가 생길때 예외를 처리하게 한다.

```
@ExceptionHandler(UserNotFoundException.class)

UserNotFoundException 예외가 발생하면 처리를 한다.
```

## @ResponseStatus

- ()안의 HTTP 응답 코드를 입력하면 HTTP 메세지에 해당 응답코드를 넣어 응답한다.

```
 @ResponseStatus(HttpStatus.NOT_FOUND)
```
