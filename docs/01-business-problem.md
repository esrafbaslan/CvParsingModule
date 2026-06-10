# Business Problem

Recruiters and hiring managers spend a significant amount of time manually reviewing candidate CVs.

The challenge becomes even more difficult when:

- Hundreds of applications are received for a single position
- Candidates submit CVs in different formats and languages
- Relevant experience is described using different terminology
- Recruiters need to compare candidates against multiple job requirements
- Recruiters are expected to screen candidates across a wide range of technical and business domains
- Skills, technologies, and certifications are often described using different acronyms, terminology, or role titles
- Identifying equivalent experience requires significant domain knowledge and manual interpretation

Traditional Applicant Tracking Systems (ATS) rely heavily on keyword matching, which often fails to identify strong candidates when skills and experiences are described differently.

For example:

- A candidate may have strong Python experience but never explicitly mention "Python Developer"
- A Data Engineer may be highly relevant for an Analytics position even when job titles do not match directly
- Multilingual CVs require additional manual effort

As a result:

- Screening becomes slow
- Recruiter workload increases
- Strong candidates may be overlooked
- Hiring decisions become less consistent

## Product Goal

The objective of the CV Parser platform was to:

1. Automatically process uploaded CVs
2. Extract structured candidate information
3. Support multilingual resumes
4. Enable semantic candidate matching
5. Reduce manual screening effort
6. Improve recruiter productivity
7. Support recruitment processes that require deep domain expertise by identifying relevant skills, experiences, and transferable competencies beyond simple keyword matching

## Success Criteria

The product was expected to:

- Reduce CV review effort
- Improve candidate discovery
- Support large candidate volumes
- Provide a scalable foundation for AI-assisted recruitment workflows
- Establish the first AI-powered capability within the Digital HR SuperApp ecosystem
- Create reusable AI architecture, evaluation, and observability patterns for future HR products
