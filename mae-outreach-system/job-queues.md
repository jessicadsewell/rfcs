# Job Queues

## Overview

The platform uses NestJS's built-in queue system with Bull/BullMQ for background job processing. This enables asynchronous processing of time-consuming tasks without blocking API responses.

For implementation details, see the [NestJS Queues documentation](https://docs.nestjs.com/techniques/queues).

## Queue Architecture

### Queue Types

- **Call Processing Queue**: Handle call scheduling, reminders, and follow-ups
- **Notification Queue**: Send emails, SMS, and push notifications
- **Data Processing Queue**: Bulk operations, data imports, and exports
- **Audit Queue**: Process audit logs and compliance reporting
- **Analytics Queue**: Generate reports and analytics data

### Implementation Pattern

- Use `@Processor()` decorator for queue handlers
- Use `@Process()` decorator for specific job types
- Use `@InjectQueue()` for dependency injection
- Follow NestJS queue patterns and best practices

## Job Types

### Call Processing Jobs

- **Schedule Call**: Create and schedule member calls
- **Automated Follow-up**: Send an email if after seven days no contact with member

### Notification Jobs

- **Send Email**: Template-based email notifications
- **Send SMS**: Text message notifications
- **Send Push Notification**: Mobile app notifications

### Data Processing Jobs

- **Bulk Import Members**: Process member data imports from CSV w/ validation

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
