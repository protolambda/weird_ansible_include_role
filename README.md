# Weird include role behavior

Inputs to role includes appear to be sticky, and do not change when continuing to the next host. (expected for imports, not for includes)

This ends up loading the wrong task, and wrong defaults, for a particular host.

The include itself is dynamic (unlike an import), but apparently the inputs to trigger the include are not.

Workaround: a single-item loop is evaluated again, taking the new variable value into account before including the role.

Compare `include_role` to `include_tasks`, task includes do handle dynamic inputs well.

