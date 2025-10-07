# Job Queues

## Overview

The platform uses NestJS's built-in queue system with Bull/BullMQ for background job processing. This enables asynchronous processing of time-consuming tasks without blocking API responses.

## Queue Architecture

| Queue Type          | Purpose                                        |
| ------------------- | ---------------------------------------------- |
| **Call Processing** | Manages call scheduling, reminders, follow-ups |
| **Notification**    | Sends emails and other notifications           |
| **Data Processing** | Handles bulk operations, imports, exports      |
| **Audit**           | Processes audit logs and compliance reports    |
| **Analytics**       | Generates reports and analytics data           |

## Job Types

### Call Processing Jobs

- **Schedule Call**: Create and schedule member calls

- **Automated Follow-up**: Send an email if after seven days no contact with member

### Notification Jobs

- **Send Email**: Template-based email notifications

### Data Processing Jobs

- **Bulk Import Members**: Process member data imports from CSV via `/api/bulk/members` endpoint

## Queue Configuration

### Redis Backend

- Redis as queue storage backend

## Queue Management

### Job Scheduling

- **Immediate Processing**: High-priority jobs processed immediately
- **Delayed Jobs**: Schedule reminders for future execution
- **Recurring Patterns**: Automated follow-up scheduling

### Monitoring

- **BullBoard Dashboard**: Visual queue management interface

## Error Handling

### Failure Management

- **Alert System**: Automated failure notifications

## References

- [NestJS Queues Documentation](https://docs.nestjs.com/techniques/queues)
- [BullMQ Documentation](https://docs.bullmq.io/)
- [BullBoard Documentation](https://github.com/felixmosh/bull-board)
- [Redis Documentation](https://redis.io/documentation)
