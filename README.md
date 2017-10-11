# SimpleThreadPool
A fast, light-weight, c++11 only thread pool.
# Example

    ThreadPool pool{ 8 };
	auto future=pool.addTask([](int i) {return 5; }, 9);
    //If you add function which have a return value,addTask will 
    //overload to the implementation which return std::future<return_type>
	pool.addTask([]() {return 5; });
    //If you add a function which reurn void type, addTask will overload to the 
    //implementation which return void.
	pool.addTask([](int i) {std::cout << "int -> void func\n"; }, 9);
	pool.addTask([](){std::cout << "void -> void func\n"; });
