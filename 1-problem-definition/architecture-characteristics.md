# Architecture Characteristics

## Top desired characteristics:

1. **Data integrity**

2. **Scalability**

3. **Availability**

4. **Security**

5. **Observability** (Auditability) <!-- Not sure about this -->

## Justification:

### Data integrity

The test grading accuracy is crucial because our whole business model depends on the credibility of our
certification.
The `SALB`could even remove our accreditation to certify architects.
See:

```
Critical Information

• As a recognized leader in certification, [...] inaccurate grading can result in a candidate not getting or maintaining a job and can impact a candidate's career.

• Inaccurate or misleading certification exams and case studies can undermine the credibility of the company’s current standing in the marketplace, so accuracy of the certification process is vital for the success of the company
```

Also, the job of 120.000 software architects depends on our system.
We cannot accidentally lose some certification data.

### Scalability

We expect a huge demand growth:

```
That number is expected to grow 5-10X based on oversees expansion as well as the
anticipated 21% growth over the next 4 years.
```

This number of candidates will stress both our IT infrastructure and our human supply of expert software architects
grading and supporting the certification process.

### Availability

With timed test, we cannot put the system under maintenance.

Fortunately:

* Only a few components need high availability
* We may have maintenance windows when test cannot start. Test cases one week early can take this into consideration

### Security

When you are in the business of providing credibility, security is a must.

Our threat model has identified a few potentially dangerous scenarios like:

* Faking accreditation
* Altering the accreditation database (Related to data integrity). Insider job?
* Denial of service (DoS) during an exam
* Getting the questions or business case ahead of the test

TODO: Finish threat model

After adding AI, we also may be concerned about

* Denial of Wallet (DoW)

### Observability (Auditability)

<!-- TODO: review this -->

We can expect `SALB` audits.

Even without them, we should be responsible for making sure that the certificate is valid.

We need AI observability to check that it works





