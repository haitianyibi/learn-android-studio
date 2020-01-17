# android包

## Manifest类

```
public final class Manifest extends Object
```

[java.lang.Object](https://developer.android.google.cn/reference/java/lang/Object.html)

android.Manifest

## R类

## R.id类

## R.layout类

## R.mipmap类

## R.string类

# java.lang包

## object类

`public class Object`

java.lang.Object

>  Class `Object` is the root of the class hierarchy. Every class has `Object` as a superclass. All objects, including arrays, implement the methods of this class
>
> object类是类等级的根，每个类都是以object类作为父类，所有对象，包括数组实现这个类的方法

| Public constructors |
| :------------------ |
| `Object()`          |

| Public methods |                                                              |
| :------------- | ------------------------------------------------------------ |
| `boolean`      | `equals(Object obj)`Indicates whether some other object is "equal to" this one. |
| `final Class`  | `getClass()`Returns the runtime class of this `Object`.      |
| `int`          | `hashCode()`Returns a hash code value for the object.        |
| `final void`   | `notify()`Wakes up a single thread that is waiting on this object's monitor. |
| `final void`   | `notifyAll()`Wakes up all threads that are waiting on this object's monitor. |
| `String`       | `toString()`Returns a string representation of the object.   |
| `final void`   | `wait(long timeout, int nanos)`Causes the current thread to wait until another thread invokes the `notify()` method or the `notifyAll()` method for this object, or some other thread interrupts the current thread, or a certain amount of real time has elapsed. |
| `final void`   | `wait(long timeout)`Causes the current thread to wait until either another thread invokes the `notify()` method or the `notifyAll()` method for this object, or a specified amount of time has elapsed. |
| `final void`   | `wait()`Causes the current thread to wait until another thread invokes the `notify()` method or the `notifyAll()` method for this object. |