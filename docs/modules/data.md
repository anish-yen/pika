# Field Tables

Header values and method arguments such as `queue_declare(arguments=...)` are AMQP field tables. pika chooses each value's field type from its Python type: `str` is sent as `S`, `bytes` as `x`, `bool` as `t`, `float` as `d` (or `f` for `Float32`), `int` as `I` or `l` (or the tag a marker type below carries), `decimal.Decimal` as `D`, `datetime` as `T`, `dict` as `F`, `list` as `A` and `None` as `V`. Import the marker types from `pika.data`: `LongLong`, `ShortShortInt`, `ShortShortUInt`, `ShortInt`, `ShortUInt`, `LongUInt` and `Float32`. Values decoded from narrow field types come back as instances of these, so a relay that re-sends a received table keeps each field's original type.

::: pika.data.LongLong

::: pika.data.ShortShortInt

::: pika.data.ShortShortUInt

::: pika.data.ShortInt

::: pika.data.ShortUInt

::: pika.data.LongUInt

::: pika.data.Float32
