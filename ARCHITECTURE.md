
# NOVA AI V2 — Architecture

## 1. Design Principles
- Reliability and security come before speed.
- Keep the code simple and maintainable.
- Test every stage before continuing.
- Use free services only.
- Never claim an untested feature works.

## 2. System Overview

The application will have four main parts:

1. Frontend: the user interface displayed in the browser.
2. Backend: a secure server endpoint that handles requests.
3. AI provider: a language model that generates real responses.
4. Hosting: services that publish the frontend and backend.

## 3. Request Flow

1. The user enters a message in the frontend.
2. The frontend sends the message to the backend over HTTPS.
3. The backend validates the request.
4. The backend securely calls the AI provider.
5. The backend returns the result to the frontend.
6. The frontend displays the answer and handles errors.

## 4. Security Boundaries
- AI API keys must only exist in backend secret storage.
- Never put secrets in frontend JavaScript or Git history.
- Never return secrets in API responses.
- Validate input types and message sizes.
- Apply sensible request limits and error handling.
- Configure cross-origin access deliberately.
- Avoid logging private conversations or credentials.

## 5. Frontend
- Responsive mobile-first layout.
- Accessible controls and readable text.
- Clear loading, success, and error states.
- Keep AI provider credentials out of browser code.
- Keep presentation code separate from backend logic.

## 6. Backend
- One documented API endpoint for chat.
- Validate incoming requests.
- Read the AI key from server-side secret storage.
- Handle provider errors and timeouts safely.
- Do not expose internal error details or secrets.
- Add appropriate request limits.

## 7. Conversation Context
- Send only the relevant conversation history.
- Validate message roles and payload sizes.
- Do not promise permanent memory until it is implemented and tested.
- Obtain consent before introducing persistent storage.

## 8. Voice and Android
These are later stages, not initial requirements for the first prototype.
- Investigate browser speech recognition and speech synthesis.
- Test browser and device compatibility.
- Evaluate continuous voice interaction separately.
- Package for Android only after the website is stable.
- Check every additional service for cost and privacy implications.

## 9. Testing
- Frontend loads on the Android tablet.
- Empty and oversized messages are rejected.
- Valid requests receive real AI responses.
- Missing or invalid credentials fail safely.
- Provider failures produce understandable errors.
- API keys never appear in browser code or responses.
- Layout works on small screens.
- No feature is marked complete without evidence.

## 10. Cost Policy
- Budget: ₹0.
- No paid subscriptions or services.
- Verify free-tier eligibility, limits, and terms before use.
- If a required feature cannot be delivered within ₹0, explain the limitation and propose alternatives.

## 11. Implementation Order
1. Documentation and repository checks.
2. Minimal frontend.
3. Frontend tests.
4. Secure backend.
5. Backend tests.
6. Real AI integration.
7. End-to-end security and reliability tests.
8. Conversation context.
9. Voice capabilities.
10. Android packaging and final review.
11. 
