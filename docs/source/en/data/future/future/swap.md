@annotate: folktale.data.future._Future.prototype.swap
category: Recovering From Errors
---

Inverts the state of a Future: successes become failures, failures become successes.


## Example::

    const { of, rejected } = require('folktale/data/future');

    of(1).swap().listen({
      onRejected: (x) => $ASSERT(x == 1)
    });

    rejected(1).swap().listen({
      onResolved: (x) => $ASSERT(x == 1)
    });
