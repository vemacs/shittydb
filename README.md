ShittyDB
========

ShittyDB is a fast, scalable key-value store written in lightweight,
asynchronous, embeddable, distributed Python. The library exposes a very
simple, easy-to-use API that is easily callable from Python and Ruby (wrappers for other
languages are forthcoming).

In Python:

```python
import shittydb
shittydb.set('foo', 'this is really fast')
shittydb.get('foo')
```

In Ruby:

```ruby
require 'shittydb'

ShittyDB.set('foo', 'this is really fast')
ShittyDB.get('foo')
```

ShittyDB is certified 100% robust and failsafe with ACID and BASE transactions.

The current release is version 0.0. Please have a look at the source code.
We are accepting all improvements and additions from the open-source
community.

FAQ
---

**Are there performance benchmarks?**

> Those are forthcoming as soon as I can find some that make it look really good.

**What is ShittyDB's story regarding consistency?**

> ShittyDB is strongly consistent and changes are written to disk on each call to `shittydb.set`.

**Are ShittyDB clients available in other languages?**

> Those are forthcoming.

**Can you change ShittyDB's name?  It's offensive and HR won't let me use it for that reason.**

> No, it's named after my grandfather.

**Does ShittyDB support SQL?**

> No, but you can write an extension to ShittyDB that handles SQL. For example:

    import re
    def shitty_sql(sql):
        match = re.match("SELECT \\* FROM ([a-z])", sql).group(1)
        return shittydb.get(match)

> Usage:

    shittydb.set("foo", "abc")
    shitty_sql("SELECT * FROM foo")

**How do you distribute ShittyDB?**

> What?

**You said up there it was a distributed key-value store.**

> Sorry, I must have misspoken.
