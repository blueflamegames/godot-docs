:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/Callable.xml.

.. _class_Callable:

Callable
========

Built-in type representing a method in an object instance or a standalone function.

.. rst-class:: classref-introduction-group

Description
-----------

**Callable** is a built-in :ref:`Variant<class_Variant>` type that represents a function. It can either be a method within an :ref:`Object<class_Object>` instance, or a standalone function not related to any object, like a lambda function. Like all :ref:`Variant<class_Variant>` types, it can be stored in variables and passed to other functions. It is most commonly used for signal callbacks.

\ **Example:**\ 


.. tabs::

 .. code-tab:: gdscript

    func print_args(arg1, arg2, arg3 = ""):
        prints(arg1, arg2, arg3)
    
    func test():
        var callable = Callable(self, "print_args")
        callable.call("hello", "world")  # Prints "hello world ".
        callable.call(Vector2.UP, 42, callable)  # Prints "(0, -1) 42 Node(Node.gd)::print_args".
        callable.call("invalid")  # Invalid call, should have at least 2 arguments.

 .. code-tab:: csharp

    public void PrintArgs(object arg1, object arg2, object arg3 = null)
    {
        GD.PrintS(arg1, arg2, arg3);
    }
    
    public void Test()
    {
        Callable callable = new Callable(this, nameof(PrintArgs));
        callable.Call("hello", "world"); // Prints "hello world null".
        callable.Call(Vector2.Up, 42, callable); // Prints "(0, -1) 42 Node(Node.cs)::PrintArgs".
        callable.Call("invalid"); // Invalid call, should have at least 2 arguments.
    }



In GDScript, it's possible to create lambda functions within a method. Lambda functions are custom callables that are not associated with an :ref:`Object<class_Object>` instance. Optionally, lambda functions can also be named. The name will be displayed in the debugger, or when calling :ref:`get_method<class_Callable_method_get_method>`.

::

    func _init():
        var my_lambda = func (message):
            print(message)
    
        # Prints Hello everyone!
        my_lambda.call("Hello everyone!")
    
        # Prints "Attack!", when the button_pressed signal is emitted.
        button_pressed.connect(func(): print("Attack!"))

.. rst-class:: classref-reftable-group

Constructors
------------

.. table::
   :widths: auto

   +---------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Callable<class_Callable>` | :ref:`Callable<class_Callable_constructor_Callable>` **(** **)**                                                                                |
   +---------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Callable<class_Callable>` | :ref:`Callable<class_Callable_constructor_Callable>` **(** :ref:`Callable<class_Callable>` from **)**                                           |
   +---------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Callable<class_Callable>` | :ref:`Callable<class_Callable_constructor_Callable>` **(** :ref:`Object<class_Object>` object, :ref:`StringName<class_StringName>` method **)** |
   +---------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`Callable<class_Callable>`     | :ref:`bind<class_Callable_method_bind>` **(** ... **)** |vararg| |const|                                    |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`Variant<class_Variant>`       | :ref:`call<class_Callable_method_call>` **(** ... **)** |vararg| |const|                                    |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | void                                | :ref:`call_deferred<class_Callable_method_call_deferred>` **(** ... **)** |vararg| |const|                  |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`Variant<class_Variant>`       | :ref:`callv<class_Callable_method_callv>` **(** :ref:`Array<class_Array>` arguments **)** |const|           |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`StringName<class_StringName>` | :ref:`get_method<class_Callable_method_get_method>` **(** **)** |const|                                     |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`Object<class_Object>`         | :ref:`get_object<class_Callable_method_get_object>` **(** **)** |const|                                     |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`int<class_int>`               | :ref:`get_object_id<class_Callable_method_get_object_id>` **(** **)** |const|                               |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`int<class_int>`               | :ref:`hash<class_Callable_method_hash>` **(** **)** |const|                                                 |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`             | :ref:`is_custom<class_Callable_method_is_custom>` **(** **)** |const|                                       |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`             | :ref:`is_null<class_Callable_method_is_null>` **(** **)** |const|                                           |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`             | :ref:`is_standard<class_Callable_method_is_standard>` **(** **)** |const|                                   |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`             | :ref:`is_valid<class_Callable_method_is_valid>` **(** **)** |const|                                         |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | void                                | :ref:`rpc<class_Callable_method_rpc>` **(** ... **)** |vararg| |const|                                      |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | void                                | :ref:`rpc_id<class_Callable_method_rpc_id>` **(** :ref:`int<class_int>` peer_id, ... **)** |vararg| |const| |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | :ref:`Callable<class_Callable>`     | :ref:`unbind<class_Callable_method_unbind>` **(** :ref:`int<class_int>` argcount **)** |const|              |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-reftable-group

Operators
---------

.. table::
   :widths: auto

   +-------------------------+------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>` | :ref:`operator !=<class_Callable_operator_neq_Callable>` **(** :ref:`Callable<class_Callable>` right **)** |
   +-------------------------+------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>` | :ref:`operator ==<class_Callable_operator_eq_Callable>` **(** :ref:`Callable<class_Callable>` right **)**  |
   +-------------------------+------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Constructor Descriptions
------------------------

.. _class_Callable_constructor_Callable:

.. rst-class:: classref-constructor

:ref:`Callable<class_Callable>` **Callable** **(** **)**

Constructs an empty **Callable**, with no object nor method bound.

.. rst-class:: classref-item-separator

----

.. rst-class:: classref-constructor

:ref:`Callable<class_Callable>` **Callable** **(** :ref:`Callable<class_Callable>` from **)**

Constructs a **Callable** as a copy of the given **Callable**.

.. rst-class:: classref-item-separator

----

.. rst-class:: classref-constructor

:ref:`Callable<class_Callable>` **Callable** **(** :ref:`Object<class_Object>` object, :ref:`StringName<class_StringName>` method **)**

Creates a new **Callable** for the method named ``method`` in the specified ``object``.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_Callable_method_bind:

.. rst-class:: classref-method

:ref:`Callable<class_Callable>` **bind** **(** ... **)** |vararg| |const|

Returns a copy of this **Callable** with one or more arguments bound. When called, the bound arguments are passed *after* the arguments supplied by :ref:`call<class_Callable_method_call>`.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_call:

.. rst-class:: classref-method

:ref:`Variant<class_Variant>` **call** **(** ... **)** |vararg| |const|

Calls the method represented by this **Callable**. Arguments can be passed and should match the method's signature.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_call_deferred:

.. rst-class:: classref-method

void **call_deferred** **(** ... **)** |vararg| |const|

Calls the method represented by this **Callable** in deferred mode, i.e. during the idle frame. Arguments can be passed and should match the method's signature.

::

    func _ready():
        grab_focus.call_deferred()

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_callv:

.. rst-class:: classref-method

:ref:`Variant<class_Variant>` **callv** **(** :ref:`Array<class_Array>` arguments **)** |const|

Calls the method represented by this **Callable**. Unlike :ref:`call<class_Callable_method_call>`, this method expects all arguments to be contained inside the ``arguments`` :ref:`Array<class_Array>`.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_get_method:

.. rst-class:: classref-method

:ref:`StringName<class_StringName>` **get_method** **(** **)** |const|

Returns the name of the method represented by this **Callable**. If the callable is a lambda function, returns the function's name.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_get_object:

.. rst-class:: classref-method

:ref:`Object<class_Object>` **get_object** **(** **)** |const|

Returns the object on which this **Callable** is called.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_get_object_id:

.. rst-class:: classref-method

:ref:`int<class_int>` **get_object_id** **(** **)** |const|

Returns the ID of this **Callable**'s object (see :ref:`Object.get_instance_id<class_Object_method_get_instance_id>`).

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_hash:

.. rst-class:: classref-method

:ref:`int<class_int>` **hash** **(** **)** |const|

Returns the 32-bit hash value of this **Callable**'s object.

\ **Note:** **Callable**\ s with equal content will always produce identical hash values. However, the reverse is not true. Returning identical hash values does *not* imply the callables are equal, because different callables can have identical hash values due to hash collisions. The engine uses a 32-bit hash algorithm for :ref:`hash<class_Callable_method_hash>`.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_is_custom:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_custom** **(** **)** |const|

Returns ``true`` if this **Callable** is a custom callable. Custom callables are created from :ref:`bind<class_Callable_method_bind>` or :ref:`unbind<class_Callable_method_unbind>`. In GDScript, lambda functions are also custom callables.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_is_null:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_null** **(** **)** |const|

Returns ``true`` if this **Callable** has no target to call the method on.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_is_standard:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_standard** **(** **)** |const|

Returns ``true`` if this **Callable** is a standard callable. This method is the opposite of :ref:`is_custom<class_Callable_method_is_custom>`. Returns ``false`` if this callable is a lambda function.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_is_valid:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_valid** **(** **)** |const|

Returns ``true`` if the callable's object exists and has a valid method name assigned, or is a custom callable.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_rpc:

.. rst-class:: classref-method

void **rpc** **(** ... **)** |vararg| |const|

Perform an RPC (Remote Procedure Call). This is used for multiplayer and is normally not available, unless the function being called has been marked as *RPC*. Calling this method on unsupported functions will result in an error.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_rpc_id:

.. rst-class:: classref-method

void **rpc_id** **(** :ref:`int<class_int>` peer_id, ... **)** |vararg| |const|

Perform an RPC (Remote Procedure Call) on a specific peer ID (see multiplayer documentation for reference). This is used for multiplayer and is normally not available unless the function being called has been marked as *RPC*. Calling this method on unsupported functions will result in an error.

.. rst-class:: classref-item-separator

----

.. _class_Callable_method_unbind:

.. rst-class:: classref-method

:ref:`Callable<class_Callable>` **unbind** **(** :ref:`int<class_int>` argcount **)** |const|

Returns a copy of this **Callable** with the arguments unbound, as defined by ``argcount``. Calling the returned **Callable** will call the method without the extra arguments that are supplied in the **Callable** on which you are calling this method.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Operator Descriptions
---------------------

.. _class_Callable_operator_neq_Callable:

.. rst-class:: classref-operator

:ref:`bool<class_bool>` **operator !=** **(** :ref:`Callable<class_Callable>` right **)**

Returns ``true`` if both **Callable**\ s invoke different targets.

.. rst-class:: classref-item-separator

----

.. _class_Callable_operator_eq_Callable:

.. rst-class:: classref-operator

:ref:`bool<class_bool>` **operator ==** **(** :ref:`Callable<class_Callable>` right **)**

Returns ``true`` if both **Callable**\ s invoke the same custom target.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
