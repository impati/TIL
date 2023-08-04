## Junit5

### assertThat().extracing 으로 컬렉션 값 테스트 하기 
---

```java
assertThat(cartItemResponses.getCartItems())
                .hasSize(2)
                .extracting("product.id", "product.name", "quantity")
                .contains(
                        tuple(1L, "Chicken", 2),
                        tuple(2L, "Pizza", 1)
                );
```


```java
public class CartItemResponses {

    private List<CartItemResponse> cartItems;

    ...
}

public class CartItemResponse {

    private final Long cartItemId;
    private final int quantity;
    private final ProductResponse product;

    ...
}


public class ProductResponse {

    private final Long id;
    private final String image;
    private final String name;
    private final int price;
    ...

}
```
cartItemResponses의 Collection 값 하나하나는 tuple 로 테스트 가능하고 
extracting("product.id", "product.name", "quantity") 순서에 맞게 tuple(..) 에 값을 삽입하여 테스트할 수 있다.
이때 테스트하고자 하는 대상이 다른 객체를 내부 필드로 가지는 경우 field.field... 로 표현 가능하다.
