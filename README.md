# worker-pool-example


Explanation:

This code demonstrates a simple worker pool pattern in Go using goroutines and channels.
	•	make(chan func(), 10) creates a buffered channel that stores functions (tasks).
It allows up to 10 tasks to be queued without blocking.
	•	The for loop with 4 iterations creates 4 worker goroutines.
Each worker continuously waits for functions from the channel and executes them.
	•	for f := range cnp keeps each worker alive and processing tasks until the channel is closed.
	•	A function that prints "HERE1" is sent into the channel to be executed by one of the workers.
	•	"HERE1" is not printed because the main() function exits immediately after printing "Hello".
When main() exits, all goroutines are terminated before they get a chance to execute the task.

Use-cases:
	•	Background job processing
	•	Task queues
	•	Concurrent request handling
	•	Worker pools
