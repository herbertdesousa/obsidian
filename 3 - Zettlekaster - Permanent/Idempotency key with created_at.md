Date: 2025-06-05
Tags: [[patterns]]

In [some Netflix paper](https://netflixtechblog.com/netflixs-distributed-counter-abstraction-8d0c45eb66b2), I just saw they using this object:
```json
{  
	"namespace": "my_dataset",  
	"counter_name": "counter123",  
	"delta": 2,  
	"idempotency_token": {  
		"token": "some_event_id",  
		"generation_time": "2024-10-05T14:48:00Z"  
	}
} 
```

It made me think, why they are using generation_time in idempotency_token? 

Well, there is another benefits, but the most important one, in my opinion is, in a scenario with multiple producers to a single consumer, while it's important to handle with order and priority, the generation_time could help by enqueuing the requests sorted by this creation time.