First we declare our variable i, and functions incrementing and decrementing.
Then we start the functions as goroutine. Consequently their execution order is unpredictable.
If we would use non-atomic i++/i-- to increment/decrement the counter, the goroutines would interfere with each other and we wouldn't get the "expected" 0. 
Thats why 'atomic.AddUint64(&i, 1)' is used, so we do get magic number 0.