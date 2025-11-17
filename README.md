# Nobelprize
api for nobelprize.org site for getting information anout nobel prize
# main
```cpp
#include "Nobelprize.h"
#include <iostream>

int main() {
   Nobelprize api;

    auto prizes = api.nobel_prizes_list().then([](json::value result) {
        std::cout << "Search results: " << result.serialize() << std::endl;
    });
    prizes.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
