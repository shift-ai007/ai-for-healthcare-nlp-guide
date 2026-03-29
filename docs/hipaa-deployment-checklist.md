# HIPAA-Compliant NLP Deployment Checklist

A practical checklist for organizations deploying NLP systems that process Protected Health Information (PHI).

## Pre-Deployment

- [ ] **BAA signed** with cloud provider (Azure/AWS/GCP Healthcare tier)
- [ ] **BAA signed** with annotation platform (if using external annotators)
- [ ] **De-identification pipeline** tested on 1,000+ real documents with manual verification
- [ ] **PHI detection recall** > 99.5% (precision can be lower — false positives are safe, false negatives are not)
- [ ] **Model hosted** in BAA-covered environment (not general-purpose endpoints)
- [ ] **Encryption at rest and in transit** for all document storage and API calls
- [ ] **Access controls** with role-based permissions (clinicians vs. coders vs. admins)
- [ ] **Audit logging** enabled for every inference request

## Model Validation

- [ ] **Test set** from target institution (not just public datasets)
- [ ] **Performance stratified** by document type (progress notes vs. discharge summaries vs. radiology)
- [ ] **Demographic parity** checked across patient populations
- [ ] **Edge cases documented** — what the model handles poorly and why
- [ ] **Confidence calibration** verified (when model says 90% confident, it's correct ~90% of the time)
- [ ] **Rollback procedure** tested — can revert to previous model version within 15 minutes

## Production Monitoring

- [ ] **Inference latency** tracked (p50, p95, p99)
- [ ] **Throughput** monitored against SLA
- [ ] **Error rate** alerting (model failures, timeout, malformed input)
- [ ] **Confidence distribution** monitored for drift (if average confidence drops, something changed)
- [ ] **Human review rate** tracked and trended
- [ ] **Annotation disagreement** rate between model and human reviewers

## Ongoing

- [ ] **Quarterly model retraining** schedule established
- [ ] **New document types** tested before enabling auto-processing
- [ ] **Staff training** for clinicians and coders interacting with NLP outputs
- [ ] **Incident response** plan for PHI exposure or model failure

---

*For a full assessment of your organization's NLP readiness, see [ShiftAI's NLP solutions](https://shift-ai.cloud/nlp-solutions/) — we specialize in building compliant, production-grade clinical NLP systems.*
