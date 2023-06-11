# Telegram System Design

Messaging Application, where people can send & recieve messages

Usecases or Functional Requirements:
- send message
- check messages
(limiting to 1 to 1 messages)
- Message type: Text

Non-functional Requirements:
- 10B messages per day (and double in an year) 
  - calculate messsage per sec (sent out per day) ~= half a million messages per sec
  - Server can handle 10K requests per sec. So, we might need 100 servers (start with 50 servers and auto-scale based on load)
  - Horizontally scaling the system 
- Msg: 100 Bytes, 10B msg = 1TB data per day = 1PB per year
- Availability? Highily Available
- Latency? 100ms (90-95% of requests)
