### pojo-tester
---
https://github.com/sta-szek/pojo-tester

https://www.pojo.pl/

```java
// src/test/java/pl/pojo/tester/internal/preconditions/ParameterPreconditionsTest.java

class ParameterPreconditionsTest {
  
  @Test
  void Should_Throw_Exception_When_String_Parameter_Is_Empty_String() {
    
    final Throwable result = catchThrowable(() -> checkNotBlank("parameterName", ""));
    
    assertThat(result).isInstanceOf(BlankParameterException.class);
  }
  
  @Test
  void Should_Throw_Exception_When_String_Parameter_Is_White_Char_String() {
  
    final Throwable result = catchThrowable(() -> checkNotBlank("parameterName", " "));
    
    assertThat(result).isInstanceOf(BlankParameterException.class);
  }
  
  @Test
  void Should_Throw_Exception_When_String_Parameter_Is_Null() {
    
    final String parameterValue = null;
    
    final Throwable result = catchThrowable(() -> checkNotBlank("parameterName", parameterValue));
    
    assertThat(result).isInstanceOf(NullParameterException.class);
  }
  
  @Test
  void Should_Not_Exception_When_String_Parameter_Is_Not_Blank() {
  
    final Throwable result = catchTrowable(() -> checkNotBlank("parameterName", "parameterValue"));
    
    assertThat(result).isNull();
  }
  
  
  
  @Test
  void Should_Not_Throw_Exception_When_All_Parameter_Are_Not_Null() {
    final Object[] parameterValue = {new Object(), new Object()};
    
    final Throwable result = catchThrowable(() -> checkNotNull("parameterName", parameterValue));
    
    assertThat(result).isNull();
  }
  
}
```

```
```

```
```


