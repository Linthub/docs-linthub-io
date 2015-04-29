---
title: Clang
layout: en
permalink: /user/clang/
---

You can use Clang Analyzer in order to find bugs in the C/C++ source code. Let's take a look at this simple C++ example:

```
#include <iostream>
#include <stdlib.h>

using namespace std;

///////////////////////////////////////////////////

int f(int* a) {
    return (*a) * 2;
}

void null_pointer1() {
    int* p = NULL;
    cout << f(p) << endl;
}
///////////////////////////////////////////////////

bool null_pointer2(int* v) {
    return (v == NULL && *v == 3);
}
///////////////////////////////////////////////////

void null_pointer_array(int *p) {
    if (p)
        return;

    int x = p[0];
    cout << x << endl;
}
///////////////////////////////////////////////////

void malloc_delete_calls() {
    int *p = (int *)malloc(sizeof(int));
    delete p;
}

///////////////////////////////////////////////////

int main(int argc, const char * argv[]) {
    null_pointer1();
    null_pointer2(NULL);
    null_pointer_array(NULL);
    malloc_delete_calls();
    return 0;
}
///////////////////////////////////////////////////
```

Clang Analyzer will generate the following warning messages for the example above:

1. Dereference of null pointer (loaded from variable 'a') (line: 10)
2. Dereference of null pointer (loaded from variable 'v') (line: 20)
3. Array access (from variable 'p') results in a null pointer dereference (line: 28)
4. Memory allocated by malloc() should be deallocated by free(), not 'delete' (line: 35)

More detailed information about Clang Analyze can be found [here](http://clang-analyzer.llvm.org).
