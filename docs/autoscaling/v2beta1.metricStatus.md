
## metricStatus
MetricStatus describes the last-read state of a single metric.

**Functions:**

[`fn .withType`](#fn-withtype)  
[`fn external.metricSelector.withMatchExpressions`](#fn-externalmetricselectorwithmatchexpressions)  
[`fn external.metricSelector.withMatchLabels`](#fn-externalmetricselectorwithmatchlabels)  
[`fn external.withCurrentAverageValue`](#fn-externalwithcurrentaveragevalue)  
[`fn external.withCurrentValue`](#fn-externalwithcurrentvalue)  
[`fn external.withMetricName`](#fn-externalwithmetricname)  
[`fn object.selector.withMatchExpressions`](#fn-objectselectorwithmatchexpressions)  
[`fn object.selector.withMatchLabels`](#fn-objectselectorwithmatchlabels)  
[`fn object.target.withName`](#fn-objecttargetwithname)  
[`fn object.withAverageValue`](#fn-objectwithaveragevalue)  
[`fn object.withCurrentValue`](#fn-objectwithcurrentvalue)  
[`fn object.withMetricName`](#fn-objectwithmetricname)  
[`fn pods.selector.withMatchExpressions`](#fn-podsselectorwithmatchexpressions)  
[`fn pods.selector.withMatchLabels`](#fn-podsselectorwithmatchlabels)  
[`fn pods.withCurrentAverageValue`](#fn-podswithcurrentaveragevalue)  
[`fn pods.withMetricName`](#fn-podswithmetricname)  
[`fn resource.withCurrentAverageUtilization`](#fn-resourcewithcurrentaverageutilization)  
[`fn resource.withCurrentAverageValue`](#fn-resourcewithcurrentaveragevalue)  
[`fn resource.withName`](#fn-resourcewithname)  

---


### `fn .withType`
type is the type of metric source.  It will be one of "Object", "Pods" or "Resource", each corresponds to a matching field in the object.
```jsonnet
{
  withType(type):: {}
}
```

### `fn external.metricSelector.withMatchExpressions`
matchExpressions is a list of label selector requirements. The requirements are ANDed.
```jsonnet
{
  withMatchExpressions(matchExpressions):: {}
}
```

### `fn external.metricSelector.withMatchLabels`
matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.
```jsonnet
{
  withMatchLabels(matchLabels):: {}
}
```

### `fn external.withCurrentAverageValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withCurrentAverageValue(currentAverageValue):: {}
}
```

### `fn external.withCurrentValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withCurrentValue(currentValue):: {}
}
```

### `fn external.withMetricName`
metricName is the name of a metric used for autoscaling in metric system.
```jsonnet
{
  withMetricName(metricName):: {}
}
```

### `fn object.selector.withMatchExpressions`
matchExpressions is a list of label selector requirements. The requirements are ANDed.
```jsonnet
{
  withMatchExpressions(matchExpressions):: {}
}
```

### `fn object.selector.withMatchLabels`
matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.
```jsonnet
{
  withMatchLabels(matchLabels):: {}
}
```

### `fn object.target.withName`
Name of the referent; More info: http://kubernetes.io/docs/user-guide/identifiers#names
```jsonnet
{
  withName(name):: {}
}
```

### `fn object.withAverageValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withAverageValue(averageValue):: {}
}
```

### `fn object.withCurrentValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withCurrentValue(currentValue):: {}
}
```

### `fn object.withMetricName`
metricName is the name of the metric in question.
```jsonnet
{
  withMetricName(metricName):: {}
}
```

### `fn pods.selector.withMatchExpressions`
matchExpressions is a list of label selector requirements. The requirements are ANDed.
```jsonnet
{
  withMatchExpressions(matchExpressions):: {}
}
```

### `fn pods.selector.withMatchLabels`
matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.
```jsonnet
{
  withMatchLabels(matchLabels):: {}
}
```

### `fn pods.withCurrentAverageValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withCurrentAverageValue(currentAverageValue):: {}
}
```

### `fn pods.withMetricName`
metricName is the name of the metric in question
```jsonnet
{
  withMetricName(metricName):: {}
}
```

### `fn resource.withCurrentAverageUtilization`
currentAverageUtilization is the current value of the average of the resource metric across all relevant pods, represented as a percentage of the requested value of the resource for the pods.  It will only be present if `targetAverageValue` was set in the corresponding metric specification.
```jsonnet
{
  withCurrentAverageUtilization(currentAverageUtilization):: {}
}
```

### `fn resource.withCurrentAverageValue`
Quantity is a fixed-point representation of a number. It provides convenient marshaling/unmarshaling in JSON and YAML, in addition to String() and AsInt64() accessors.

The serialization format is:

<quantity>        ::= <signedNumber><suffix>
  (Note that <suffix> may be empty, from the "" case in <decimalSI>.)
<digit>           ::= 0 | 1 | ... | 9 <digits>          ::= <digit> | <digit><digits> <number>          ::= <digits> | <digits>.<digits> | <digits>. | .<digits> <sign>            ::= "+" | "-" <signedNumber>    ::= <number> | <sign><number> <suffix>          ::= <binarySI> | <decimalExponent> | <decimalSI> <binarySI>        ::= Ki | Mi | Gi | Ti | Pi | Ei
  (International System of units; See: http://physics.nist.gov/cuu/Units/binary.html)
<decimalSI>       ::= m | "" | k | M | G | T | P | E
  (Note that 1024 = 1Ki but 1000 = 1k; I didn't choose the capitalization.)
<decimalExponent> ::= "e" <signedNumber> | "E" <signedNumber>

No matter which of the three exponent forms is used, no quantity may represent a number greater than 2^63-1 in magnitude, nor may it have more than 3 decimal places. Numbers larger or more precise will be capped or rounded up. (E.g.: 0.1m will rounded up to 1m.) This may be extended in the future if we require larger or smaller quantities.

When a Quantity is parsed from a string, it will remember the type of suffix it had, and will use the same type again when it is serialized.

Before serializing, Quantity will be put in "canonical form". This means that Exponent/suffix will be adjusted up or down (with a corresponding increase or decrease in Mantissa) such that:
  a. No precision is lost
  b. No fractional digits will be emitted
  c. The exponent (or suffix) is as large as possible.
The sign will be omitted unless the number is negative.

Examples:
  1.5 will be serialized as "1500m"
  1.5Gi will be serialized as "1536Mi"

Note that the quantity will NEVER be internally represented by a floating point number. That is the whole point of this exercise.

Non-canonical values will still parse as long as they are well formed, but will be re-emitted in their canonical form. (So always use canonical form, or don't diff.)

This format is intended to make it difficult to use these numbers without writing some sort of special handling code in the hopes that that will cause implementors to also use a fixed point implementation.
```jsonnet
{
  withCurrentAverageValue(currentAverageValue):: {}
}
```

### `fn resource.withName`
name is the name of the resource in question.
```jsonnet
{
  withName(name):: {}
}
```
