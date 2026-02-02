# Changelog

## [Unreleased] - 2026-02-02

### Added
- **Conditional USE-JWT-COOKIE Header**: Added `skipUseJwtCookieHeader` flag support in JWT token provider interceptor
  - When `axiosRequestConfig.skipUseJwtCookieHeader` is set to `true`, the interceptor skips adding the `USE-JWT-COOKIE` header
  - This allows MFEs to suppress the header when using session cookie authentication (e.g., direct access without iframe)
  - Prevents CORS preflight failures caused by the custom header when the server does not whitelist it

### Files Modified
- `src/auth/interceptors/createJwtTokenProviderInterceptor.js` - Conditional `USE-JWT-COOKIE` header
