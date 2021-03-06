[shark](../../index.md) / [shark](../index.md) / [ObjectInspector](./index.md)

# ObjectInspector

`interface ObjectInspector`

Provides LeakCanary with insights about objects (classes, instances and arrays) found in the
heap. [inspect](inspect.md) will be called for each object that LeakCanary wants to know more about.
The implementation can then use the provided [ObjectReporter](../-object-reporter/index.md) to provide insights for that
object.

You can create a [ObjectInspector](./index.md) from a lambda by calling [invoke](invoke.md).

### Functions

| Name | Summary |
|---|---|
| [inspect](inspect.md) | `abstract fun inspect(reporter: `[`ObjectReporter`](../-object-reporter/index.md)`): `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html) |

### Companion Object Functions

| Name | Summary |
|---|---|
| [invoke](invoke.md) | `operator fun invoke(block: (`[`ObjectReporter`](../-object-reporter/index.md)`) -> `[`Unit`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-unit/index.html)`): `[`ObjectInspector`](./index.md)<br>Utility function to create a [ObjectInspector](./index.md) from the passed in [block](invoke.md#shark.ObjectInspector.Companion$invoke(kotlin.Function1((shark.ObjectReporter, kotlin.Unit)))/block) lambda instead of using the anonymous `object : OnHeapAnalyzedListener` syntax. |

### Inheritors

| Name | Summary |
|---|---|
| [AppSingletonInspector](../-app-singleton-inspector/index.md) | `class AppSingletonInspector : `[`ObjectInspector`](./index.md)<br>Inspector that automatically marks instances of the provided class names as not leaking because they're app wide singletons. |
| [ObjectInspectors](../-object-inspectors/index.md) | `enum class ObjectInspectors : `[`ObjectInspector`](./index.md)<br>A set of default [ObjectInspector](./index.md)s that knows about common JDK objects. |
