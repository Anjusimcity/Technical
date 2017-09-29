@JsonInclude
------------

Annotation used to indicate when value of the annotated property (when used for a field, method or constructor parameter), or all  properties of the annotated class, is to be serialized. 
Without annotation property values are always included, but by using this annotation one can specify simple exclusion rules to reduce amount of properties to write out.

      _@JsonInclude(Include.NOT_NULL)_
      _String name_
  
Here NOT_NULL will say json to include properties only when name is non-null value.
