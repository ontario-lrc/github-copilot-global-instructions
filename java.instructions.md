---
description: Use when writing, changing, or reviewing Java code.
applyTo: "**/*.java"
---

# Java

- Never use raw types. Write `List<String>` rather than `List`, and `Map<String, CustomerAccount>` rather than `Map`.
- Name `final` fields in upper snake case, such as `static final int MAXIMUM_RETRY_COUNT = 3;`.
- Implement lookup maps with `Map<KeyType, ValueType>`.

Brace style:

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
