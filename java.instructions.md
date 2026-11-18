---
description: Apply Java-specific type-safety, naming, collection, and formatting conventions.
applyTo: "**/*.java"
---

# Java

- Do not use raw generic types. Prefer `List<String>` to `List` and `Map<String, CustomerAccount>` to `Map`.
- Use lower camel case for variables, methods, parameters, and instance fields, including `final` instance fields.
- Use UPPER_SNAKE_CASE for `static final` constants, consistent with Java conventions.
- Use `Map<KeyType, ValueType>` for typed key-to-value lookups.
- Prefer standard language and project conventions over cosmetic refactoring.

Brace style when the project does not define another formatter convention:

```java
public final class CustomerAccountValidator
{
	public boolean isValid(CustomerAccount customerAccount)
	{
		if(customerAccount == null)
		{
			return false;
		}

		return customerAccount.hasVerifiedEmailAddress();
	}
}
```
