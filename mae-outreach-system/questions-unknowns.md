# Unknowns & Open Questions

## Technical Decisions

### Database & Performance

- **Database Sharding**: "if needed" - what are the scaling triggers?
- **Connection Pooling**: Specific pool sizes and limits per service
- **Caching Strategy**: Redis usage beyond job queues - response caching?
- **Backup Strategy**: Specific RTO/RPO requirements for HIPAA compliance

## Business & Compliance

### Data & Integration

- **CSV Consistency**: Format standardization across insurance plans
- **CSV Content**: What specific fields are provided by each plan?
- **Data Retention**: Specific HIPAA retention periods for different data types
- **Audit Requirements**: What level of audit logging is required by each plan?

### User Management

- **Specialist Onboarding**: How are new specialists added and trained?
- **Role Definitions**: Specific permissions for different user types
- **Multi-tenancy**: How to handle multiple insurance plans in same system?

### Risk Management

- **Risk Scoring**: Algorithm details for automated risk assessment
- **Report Generation**: Automated?

## Operational Questions

### Security

- **PHI Encryption**: Specific encryption standards and key management
- **Access Controls**: How granular should permissions be?

## Product Enhancement Ideas

- User management of Outreach specialists
- Dashboard for Outreach specialists to view members assigned to them
- Report generation
- Data ingestion from certain clinics or providers
- Real-time notifications for high-risk cases
- Mobile app for specialists (future consideration)
- Integration with electronic health records (EHR) systems
