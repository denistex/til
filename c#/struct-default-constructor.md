# Struct Default Constructor

It is not possible to define a custom default constructor for structs in
C#. The compiler automatically provides a default constructor that
initializes all fields to their default values.

Even if there is a single parametrized contructor defined for a struct,
it is still possible to create an instance by calling the default
constructor.

