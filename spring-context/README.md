
### v4.3.7.RELEASE
[Refer class from tag v4.3.7.RELEASE](https://github.com/DropwizardOz/spring-framework/blob/v4.3.7.RELEASE/spring-context/src/main/java/org/springframework/context/annotation/AnnotationConfigApplicationContext.java)

### the signature of AnnotationConfigApplicationContext
public class AnnotationConfigApplicationContext extends GenericApplicationContext implements AnnotationConfigRegistry

### AnnotationConfigRegistry Interface
1. 2 method: register() and scan()
1.1 register(Class<?>... annotatedClasses)
1.2 scan(String... basePackages)

### Architecture
```
AbstractApplicationContext
	-> GenericApplicationContext 
		-> AnnotationConfigApplicationContext
```
### construct method

```
L81 ~ L85
	public AnnotationConfigApplicationContext(Class<?>... annotatedClasses) {
		this();
		register(annotatedClasses);
		refresh();
	}
```

1. annotatedClasses is annotation config class
2. register the config class
3. refresh the context, implemented by the super class
	org.springframework.context.support.AbstractApplicationContext#refresh()



