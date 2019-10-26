# atomic_shared_ptr 

My take on an atomic shared pointer. 

- Lock-Free (if used with a lock-free allocator)
- Uses an interface resembling that of an std::atomic type
- Uses internal versioning to protect against ABA problems
- Uses a shared_ptr similar to that of std::shared_ptr

------

Single header include atomic_shared_ptr.h, optionally atomic_shared_ptr.natvis for better debug viewing in Visual Studio

There are four different versions of compare_exchange_strong, two of which take raw_ptr as expected value. These are non-reference counted representations of shared_ptr/atomic_shared_ptr. The raw_ptr may be used if shared ownership is not needed of the expected out value, as the shared_ptr variants incur extra costs upon failure.
