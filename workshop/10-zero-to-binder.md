# From Zero to Binder!

This document will walk you through taking a repository containing Python
code and adding to it to make it runnable with a service like mybinder.org.

One of the big hurdles to trying out other people's code is reproducing the
exact environment that the code requires to run. Writing instructions that
are correct for all possible cases is very hard. As a user applying imperfect
instructions to your particular setup is very hard. Often it is also not clear
where the "bug" is when things don't work. Should the instructions have mentioned
that setting that obscure environment variable to an obscure value would break
the instructions? Should you as user have know this? And will either the author
or the user ever think of checking for obscure things like this?

One way to solve this is the approach BinderHub (the software behind
mybinder.org) takes. The authors provide machine-readable instructions for how
to construct the environment. A machine will execute these instructions and if
they do not work, it is clear the instructions need updating. The construction
of the environment starts from the same "base" for every possible project, which
makes it easier for users to help out with fixing the instructions.


## Creating a repository to "binderize"
