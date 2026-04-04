# Verification and Onboarding

The verification and onboarding process is the gatekeeper for Operation Substrate Garden.

## 1. Secure Whitelisting
- **Definition:** Only users from pre-approved organizations (military and civilian) can join.
- **Domain Verification:** Allowed organizations are defined by authorized email domains. Platform administrators are responsible for whitelisting these allowed e-mail domains.
- **Verification:** Users must verify their organization membership during sign-up through enterprise identity providers (e.g., SSO/SAML) or authorized email domains.
- **Auditing:** All whitelist entries are reviewed and audited on a regular basis by platform administrators.

## 2. Onboarding Workflow
- **Sign-Up:** Users provide their organization email or connect through SSO.
- **Email Confirmation:** Upon registration, users receive a confirmation email sent to their official whitelisted domain.
- **Verification Flow:** Clicking the sign-up link in the confirmation email redirects the user to a dedicated verification flow.
- **Passkey Setup:** During the verification flow, users must set up a Passkey (e.g., mobile passkey or Yubikey) as their mandatory authentication method. The device must support FIDO2.
- **Profile Setup:** Users create a professional profile, listing their interests and expertise.
- **Community Discovery:** After verification, users are presented with a curated list of communities based on their profile and organization.
- **Tutorial:** A brief, interactive walkthrough of the Substrate Map and Community structures.

## 3. UI/UX for Onboarding
- **Confidence-Building Design:** The sign-up and verification screens must look authoritative and secure, using the "Tactical Elegance" design system.
- **Clear Status:** At each step, users are informed of their verification status and what information is still needed.
- **Warmth:** Despite the security measures, the onboarding language must remain welcoming and clear.
