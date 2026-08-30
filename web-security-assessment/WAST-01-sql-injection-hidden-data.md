# WAST-01: SQL Injection in Product Category Filter

## Assessment Information

| Field | Details |
|---|---|
| Assessment ID | WAST-01 |
| Assessment Type | Authorized Web Application Security Training Lab |
| Platform | PortSwigger Web Security Academy |
| Lab Title | SQL injection vulnerability in WHERE clause allowing retrieval of hidden data |
| Vulnerability Category | SQL Injection |
| OWASP Category | Injection |
| Assessment Date | 31 August 2026 |
| Tester | Sourab Palrecha |
| Testing Tool | Burp Suite Community Edition |
| Scope | Controlled and authorized PortSwigger training lab only |

## Executive Summary

A SQL Injection vulnerability was identified in the product-category filtering functionality of an authorized PortSwigger Web Security Academy training lab.

The application accepted user-controlled input through the product category parameter and incorporated this input into a database query without sufficient protection. By modifying the category parameter using Burp Suite, the intended query logic was altered and the application displayed products that were not intended to be publicly available.

In a production environment, a vulnerability of this type could enable unauthorized access to sensitive information, exposure of unpublished business data, bypass of application restrictions, and potentially more serious database compromise depending on the database permissions and application design.

## Severity Assessment

**Severity: High**

The vulnerability is rated High for this training scenario because it allowed unauthorized retrieval of hidden or unreleased product information by manipulating a user-controlled request parameter.

Actual production severity would depend on factors including:

- Sensitivity of accessible data
- Database account privileges
- Ability to extract, alter, or delete data
- Authentication and authorization controls
- Network exposure
- Logging and detection capabilities

## Vulnerability Description

SQL Injection occurs when an application includes untrusted user input in a SQL query without using parameterized queries, prepared statements, or appropriate input validation.

The product-category filter accepted a user-controlled category value. The application used this value in a database query intended to return products belonging to the selected category and marked as released.

Insufficient input handling enabled an attacker to alter the logical condition of the backend SQL query. This caused the application to return products that were not intended to be visible to normal users.

## Affected Functionality

| Component | Details |
|---|---|
| Application Function | Product category filtering |
| Input Location | User-controlled category request parameter |
| HTTP Method | GET |
| Security Issue | Unsafe handling of input in a database query |
| Impacted Data | Hidden or unreleased product records in the training environment |

## Assessment Methodology

The following authorized assessment process was used:

1. Accessed the PortSwigger lab using Burp Suite's built-in browser.
2. Navigated to the product-category filtering function.
3. Captured the HTTP request using Burp Suite Proxy and HTTP History.
4. Identified the user-controlled `category` parameter.
5. Sent the request to Burp Suite Repeater.
6. Modified the category parameter in the authorized lab environment.
7. Sent the modified request and compared the response with the normal application response.
8. Confirmed that the modified request caused unreleased products to be displayed.
9. Documented the risk, impact, and remediation recommendations.

## Evidence

Burp Suite Proxy captured an HTTP GET request generated when a product category was selected.

The request contained a user-controlled `category` parameter. Testing this parameter in Burp Suite Repeater demonstrated that modifying the input altered the backend query logic and caused the application to return hidden or unreleased products.

Technical request values, session information, lab instance URLs, and the complete proof-of-concept payload have been intentionally excluded from this public portfolio report.

## Potential Business Impact

If this vulnerability were present in a production web application, potential impacts could include:

- Unauthorized access to unpublished or sensitive business information
- Exposure of customer, product, financial, or operational data
- Bypass of intended application restrictions
- Increased risk of further database attacks
- Regulatory and compliance concerns
- Reputational damage and loss of customer trust

## Root Cause

The likely root cause is insecure construction of a SQL query using untrusted user-supplied input.

The application did not adequately separate user input from SQL query logic. This allowed input supplied through the category filter to influence the condition used by the database query.

## Remediation Recommendations

1. Use parameterized queries or prepared statements for every database query.
2. Do not build SQL queries through string concatenation with user-controlled input.
3. Apply server-side allow-list validation for category values where appropriate.
4. Use database accounts with least-privilege permissions.
5. Ensure database error messages are not exposed to application users.
6. Conduct secure code reviews and regular web-application security testing.
7. Implement centralized logging and alerting for suspicious request patterns.
8. Consider a web application firewall as an additional defense layer, but not as a replacement for secure coding.

## Validation Recommendation

After remediation, retest the category filter to confirm that modified or unexpected input does not alter query logic or expose unreleased records.

## Key Lessons Learned

- User-controlled input must never be directly incorporated into SQL query logic.
- Burp Suite Proxy and Repeater are effective tools for capturing, modifying, and validating HTTP requests in authorized assessment environments.
- A successful vulnerability assessment must include risk context, evidence, business impact, remediation, and retesting recommendations.
- Security findings should be documented without exposing unnecessary sensitive data or reusable exploit details.

## Authorization Statement

All testing documented in this report was performed solely within a controlled, intentionally vulnerable, and authorized PortSwigger Web Security Academy training environment. No employer systems, client systems, public websites, or unauthorized targets were tested.
