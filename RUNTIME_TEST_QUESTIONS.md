# Runtime-Based Developer Test Questions
## Questions That Require Running the Project

These questions can **ONLY** be answered by actually running, testing, and interacting with the live application. They test practical, hands-on experience rather than just code reading.

---

## 🚀 Setup & Initial Run

### Q1: Project Startup
**Question:** When you run `npm run dev`, what happens? Describe the exact sequence:
- Which ports are used?
- What console messages appear?
- What errors (if any) occur on first run?
- How long does it take to start?

**What This Tests:** Ability to set up and run the project, understanding of the development environment.

---

### Q2: Database Connection
**Question:** What happens when you try to register a new user? Does it work? What error messages appear (if any)?

**What This Tests:** Understanding of database configuration, error handling, ability to diagnose connection issues.

---

### Q3: Environment Variables
**Question:** What environment variables are required for the project to run? Which ones cause the app to crash if missing, and which ones just disable features?

**What This Tests:** Understanding of configuration, ability to identify required vs optional settings.

---

## 🎨 Frontend Behavior

### Q4: Homepage Load
**Question:** When you visit `http://localhost:3000`, what exactly loads? 
- What API calls are made?
- In what order?
- How long does each take?
- What's visible before data loads?

**What This Tests:** Understanding of loading states, API integration, user experience.

---

### Q5: Wallet Connection Flow
**Question:** Connect a wallet (MetaMask or any supported wallet). Describe the exact flow:
- What happens when you click "Connect Wallet"?
- What prompts appear?
- What data is stored where?
- What happens if you reject the connection?
- What happens if you switch networks?

**What This Tests:** Understanding of Web3 integration, wallet connection flow, error handling.

---

### Q6: Steam OAuth Flow
**Question:** Try to sign in with Steam. Describe the complete flow:
- What URL does it redirect to?
- What happens after Steam authentication?
- Where is the token stored?
- What happens if you close the popup?
- How does it work on mobile vs desktop?

**What This Tests:** Understanding of OAuth flow, cross-window communication, mobile handling.

---

### Q7: Gamer Dashboard Behavior
**Question:** Navigate to `/gamer` page. What happens:
- If you're not connected to a wallet?
- If you're connected but haven't linked Steam?
- If you've linked Steam but haven't claimed?
- What data is displayed and where does it come from?

**What This Tests:** Understanding of conditional rendering, state management, data flow.

---

### Q8: Developer Dashboard Behavior
**Question:** Navigate to `/developer` page. 
- What tabs are available?
- What happens when you switch tabs?
- What API calls are triggered?
- What's the difference between "Verify my Steam games" and "My P12 tokens" tabs?

**What This Tests:** Understanding of tab navigation, component lifecycle, API integration.

---

### Q9: Real-time Updates
**Question:** On the homepage rankings, do they update automatically? 
- How often?
- What triggers updates?
- Do you see loading states?
- What happens if the API is slow?

**What This Tests:** Understanding of polling, caching, loading states, error handling.

---

### Q10: Error States
**Question:** Intentionally break something (disconnect internet, wrong API URL, etc.). What error messages appear? 
- Are they user-friendly?
- Do they help debug?
- Where are errors displayed?

**What This Tests:** Understanding of error handling, user experience, debugging capabilities.

---

## 🔐 Authentication & Security

### Q11: JWT Token Behavior
**Question:** After logging in, where is the JWT token stored?
- Check cookies, localStorage, sessionStorage
- What's the token expiration?
- What happens when it expires?
- Can you see the token content?

**What This Tests:** Understanding of authentication mechanisms, token storage, security practices.

---

### Q12: Protected Routes
**Question:** Try accessing `/gamer` or `/developer` without authentication. What happens?
- Are you redirected?
- What error appears?
- Can you bypass it?

**What This Tests:** Understanding of route protection, authentication checks.

---

### Q13: Wallet Signature Verification
**Question:** When you sign a message with your wallet, what exactly is being signed?
- What message format is used?
- Where is the signature verified?
- What happens if verification fails?

**What This Tests:** Understanding of SIWE (Sign-In with Ethereum), signature verification.

---

## 📊 Data Flow & API

### Q14: API Request Flow
**Question:** Open browser DevTools Network tab. When you load the gamer page:
- How many API requests are made?
- What are the endpoints?
- What's the request/response format?
- Which requests can be cached?
- Are there any failed requests?

**What This Tests:** Understanding of API architecture, request optimization, debugging skills.

---

### Q15: React Query Caching
**Question:** Load the gamer page, then navigate away and back. 
- Are API calls made again?
- How long is data cached?
- What triggers a refetch?
- Can you see stale data?

**What This Tests:** Understanding of React Query caching, stale-while-revalidate pattern.

---

### Q16: State Management Flow
**Question:** Connect wallet → Link Steam → View gamer page. 
- What Recoil atoms are updated?
- In what order?
- Can you see the updates in React DevTools?
- What components re-render?

**What This Tests:** Understanding of state management, component re-rendering, debugging tools.

---

## 🎯 Feature-Specific Behavior

### Q17: NFT Badge Display
**Question:** If you have a claimable NFT, what happens when you click "Claim"?
- What URL does it open?
- Is it Galxe?
- What data is passed?
- What happens after claiming?

**What This Tests:** Understanding of NFT minting flow, external integrations.

---

### Q18: Token Display
**Question:** On the gamer/developer page, how are token amounts displayed?
- Are they formatted?
- Do they show "?,???" or actual numbers?
- What determines which is shown?
- Are they clickable?

**What This Tests:** Understanding of data formatting, conditional display logic.

---

### Q19: Rankings Behavior
**Question:** On the homepage rankings:
- How many users are shown?
- Is there pagination?
- Can you sort?
- How often do rankings update?
- What happens if you're at the bottom?

**What This Tests:** Understanding of pagination, data display, user experience.

---

### Q20: Collab Modal
**Question:** Click "View all collabs" button. 
- What modal opens?
- What data is displayed?
- How is it loaded?
- Can you interact with it?
- What happens on mobile?

**What This Tests:** Understanding of modal implementation, responsive design, data loading.

---

## 🐛 Error Scenarios

### Q21: Network Failures
**Question:** Simulate network failure (turn off WiFi, block requests). 
- What happens to the UI?
- Are errors displayed?
- Can you retry?
- Is data preserved?

**What This Tests:** Understanding of error handling, offline behavior, resilience.

---

### Q22: Slow API Responses
**Question:** Throttle network to "Slow 3G" in DevTools. 
- What loading states appear?
- How long do they show?
- Is the UI responsive?
- Can users interact while loading?

**What This Tests:** Understanding of loading states, user experience, performance optimization.

---

### Q23: Invalid Wallet Address
**Question:** Try to use an invalid wallet address format. 
- What validation occurs?
- When does it happen (on input, on submit)?
- What error message appears?
- Can you bypass validation?

**What This Tests:** Understanding of input validation, error handling, security.

---

### Q24: Wrong Network
**Question:** Connect wallet on wrong network (e.g., Ethereum when BSC is required). 
- What happens?
- Is there a network switch prompt?
- What error appears?
- Can you proceed?

**What This Tests:** Understanding of network validation, user guidance, error prevention.

---

## 📱 Responsive & Mobile

### Q25: Mobile Behavior
**Question:** Test on mobile device or mobile viewport (375px width). 
- What breaks?
- What's different from desktop?
- How does Steam OAuth work?
- Are touch interactions smooth?

**What This Tests:** Understanding of responsive design, mobile UX, cross-platform compatibility.

---

### Q26: Tablet View
**Question:** Test on tablet viewport (768px). 
- How does layout adapt?
- Are components rearranged?
- Is navigation different?
- What's the optimal experience?

**What This Tests:** Understanding of responsive breakpoints, layout systems.

---

## ⚡ Performance

### Q27: Initial Load Time
**Question:** Measure the initial page load:
- Time to First Contentful Paint (FCP)
- Time to Interactive (TTI)
- Total bundle size
- Number of requests
- What's the bottleneck?

**What This Tests:** Understanding of performance metrics, optimization awareness.

---

### Q28: Bundle Analysis
**Question:** Run `npm run build` and analyze the bundle:
- What are the largest chunks?
- Are there duplicate dependencies?
- What could be code-split?
- Total bundle size?

**What This Tests:** Understanding of build optimization, bundle analysis tools.

---

### Q29: Re-render Analysis
**Question:** Use React DevTools Profiler. Navigate through the app:
- Which components re-render unnecessarily?
- What causes re-renders?
- Are there performance issues?
- What would you optimize?

**What This Tests:** Understanding of React performance, profiling tools, optimization.

---

### Q30: API Response Times
**Question:** Monitor API response times in Network tab:
- Which endpoints are slowest?
- Average response time?
- Any timeouts?
- What's causing slowness?

**What This Tests:** Understanding of API performance, backend awareness, optimization.

---

## 🔄 State & Data Persistence

### Q31: Page Refresh Behavior
**Question:** Connect wallet, link Steam, then refresh the page:
- What state is preserved?
- What's lost?
- What needs to be re-fetched?
- How long until full state restored?

**What This Tests:** Understanding of state persistence, data fetching, user experience.

---

### Q32: LocalStorage Usage
**Question:** Check browser localStorage and sessionStorage:
- What's stored?
- When is it set?
- When is it cleared?
- Is sensitive data stored?

**What This Tests:** Understanding of client-side storage, security practices.

---

### Q33: Cookie Usage
**Question:** Check browser cookies:
- What cookies are set?
- What are their purposes?
- Expiration times?
- HttpOnly flags?
- SameSite settings?

**What This Tests:** Understanding of cookie management, security practices.

---

## 🎨 UI/UX Details

### Q34: Loading States
**Question:** Throughout the app, identify all loading states:
- Spinners, skeletons, placeholders?
- Are they consistent?
- Do they provide feedback?
- Any missing loading states?

**What This Tests:** Understanding of UX patterns, loading state implementation.

---

### Q35: Animations
**Question:** What animations are used?
- Page transitions?
- Component animations?
- Hover effects?
- Are they smooth (60fps)?

**What This Tests:** Understanding of animation libraries, performance, UX polish.

---

### Q36: Toast Notifications
**Question:** Trigger various actions (success, error, etc.):
- What toast library is used?
- Where do toasts appear?
- How long do they show?
- Can you stack multiple?
- Are they accessible?

**What This Tests:** Understanding of notification systems, accessibility.

---

### Q37: Form Validation
**Question:** Find all forms in the app:
- What validation occurs?
- When (on blur, on submit)?
- Error message display?
- Are errors helpful?

**What This Tests:** Understanding of form handling, validation patterns, UX.

---

## 🔗 External Integrations

### Q38: Galxe Integration
**Question:** If you have a claimable NFT, click claim:
- What URL opens?
- What parameters are passed?
- How is the callback handled?
- What happens after claiming?

**What This Tests:** Understanding of external integrations, OAuth-like flows.

---

### Q39: Steam API Integration
**Question:** When Steam data is fetched:
- What Steam API endpoints are called?
- What data is retrieved?
- How is it processed?
- What happens if Steam API is down?

**What This Tests:** Understanding of external API integration, error handling.

---

### Q40: Cloudinary Integration
**Question:** If there's image upload functionality:
- How are images uploaded?
- What transformations are applied?
- Where are URLs stored?
- What's the upload flow?

**What This Tests:** Understanding of file upload, CDN integration, image optimization.

---

## 🧪 Testing Scenarios

### Q41: Multiple Tabs
**Question:** Open the app in multiple browser tabs:
- Does state sync?
- What happens if you connect wallet in one tab?
- Are there race conditions?
- How is state managed?

**What This Tests:** Understanding of multi-tab behavior, state synchronization.

---

### Q42: Browser Back/Forward
**Question:** Navigate through the app, use browser back/forward:
- Does state persist?
- Are API calls repeated?
- Is history managed correctly?
- Any issues?

**What This Tests:** Understanding of browser history, state management, navigation.

---

### Q43: Concurrent Actions
**Question:** Perform multiple actions quickly (connect wallet, link Steam, navigate):
- Any race conditions?
- Are requests cancelled properly?
- Does UI stay consistent?
- Any errors?

**What This Tests:** Understanding of async handling, race conditions, request management.

---

## 🔍 Debugging Scenarios

### Q44: Console Errors
**Question:** Open browser console:
- What errors appear on load?
- What warnings?
- Are they critical?
- What would you fix first?

**What This Tests:** Understanding of debugging, error identification, prioritization.

---

### Q45: Network Tab Analysis
**Question:** Analyze Network tab during normal usage:
- Any failed requests?
- Any slow requests?
- Any unnecessary requests?
- What would you optimize?

**What This Tests:** Understanding of network optimization, API efficiency.

---

### Q46: React DevTools Analysis
**Question:** Use React DevTools to inspect:
- Component tree structure
- Props being passed
- State values
- Any issues you notice?

**What This Tests:** Understanding of React debugging, component architecture.

---

## 🎯 Real-World Scenarios

### Q47: New User Journey
**Question:** As a completely new user:
1. Visit homepage
2. Connect wallet
3. Link Steam account
4. View gamer dashboard
5. Check rankings

Describe the complete journey, what works, what doesn't, what's confusing.

**What This Tests:** Understanding of user experience, onboarding flow, usability.

---

### Q48: Developer Verification Flow
**Question:** As a developer:
1. Connect wallet
2. Navigate to developer page
3. Try to verify a game
4. Check verification status
5. View tokens

Describe the flow, identify pain points, suggest improvements.

**What This Tests:** Understanding of developer workflow, feature comprehension.

---

### Q49: Error Recovery
**Question:** Intentionally cause errors (wrong network, API failure, etc.):
- How does the app recover?
- Are users guided?
- Can they continue?
- What's the error experience?

**What This Tests:** Understanding of error recovery, user guidance, resilience.

---

### Q50: Complete Feature Test
**Question:** Test the complete airdrop claim flow:
1. Connect wallet
2. Link Steam/Verify game
3. View eligible rewards
4. Claim NFT
5. Verify on Galxe
6. Check token balance

Document every step, what works, what breaks, what's missing.

**What This Tests:** End-to-end understanding, feature completeness, quality assurance mindset.

---

## 📋 Answer Format

For each question, candidates should provide:
1. **Observation:** What they actually see/experience
2. **Analysis:** Why it works that way
3. **Issues:** Any problems they notice
4. **Improvements:** What they would change

---

## 🎯 Evaluation Criteria

### Excellent (5/5)
- ✅ Detailed observations with specific examples
- ✅ Accurate analysis of why things work
- ✅ Identifies issues and edge cases
- ✅ Suggests concrete improvements
- ✅ Uses debugging tools effectively

### Good (4/5)
- ✅ Good observations
- ✅ Generally correct analysis
- ✅ Some issues identified
- ⚠️ Improvements could be more specific

### Satisfactory (3/5)
- ✅ Basic observations
- ⚠️ Limited analysis
- ⚠️ Misses some issues
- ⚠️ Vague improvements

### Needs Improvement (2/5)
- ⚠️ Superficial observations
- ❌ Incorrect analysis
- ❌ Misses major issues
- ❌ No improvement suggestions

### Poor (1/5)
- ❌ Can't run the project
- ❌ No meaningful observations
- ❌ Incorrect understanding
- ❌ No analysis

---

## 🚀 Setup Instructions for Candidates

Provide these instructions:

1. **Clone and Install:**
   ```bash
   git clone <repo>
   cd micro1-p12-skill-test
   npm install
   ```

2. **Configure Environment:**
   - Copy `.env.example` to `.env`
   - Fill in required variables (at minimum: API URLs)

3. **Start Development:**
   ```bash
   npm run dev
   ```

4. **Open Browser:**
   - Frontend: `http://localhost:3000`
   - Backend: `http://localhost:3099`

5. **Have Ready:**
   - Browser DevTools (Console, Network, React DevTools)
   - MetaMask or other Web3 wallet
   - Steam account (for testing Steam features)

---

## ⏱️ Recommended Test Structure

### Quick Test (60 minutes)
- Q1, Q4, Q5, Q6, Q11, Q14, Q21, Q27, Q44, Q47
- **Focus:** Basic functionality, errors, performance

### Standard Test (120 minutes)
- All Q1-Q30
- **Focus:** Comprehensive understanding

### Comprehensive Test (180 minutes)
- All questions Q1-Q50
- **Focus:** Deep analysis and improvements

---

## 📊 Scoring

- **Setup & Run (Q1-Q3):** 15 points
- **Frontend Behavior (Q4-Q10):** 35 points
- **Authentication (Q11-Q13):** 15 points
- **Data Flow (Q14-Q16):** 15 points
- **Features (Q17-Q20):** 20 points
- **Errors (Q21-Q24):** 20 points
- **Responsive (Q25-Q26):** 10 points
- **Performance (Q27-Q30):** 20 points
- **State (Q31-Q33):** 15 points
- **UI/UX (Q34-Q37):** 20 points
- **Integrations (Q38-Q40):** 15 points
- **Testing (Q41-Q43):** 15 points
- **Debugging (Q44-Q46):** 15 points
- **Real-World (Q47-Q50):** 20 points

**Total: 250 points**

**Passing Thresholds:**
- Junior: 50% (125 points)
- Mid-Level: 65% (163 points)
- Senior: 80% (200 points)
- Lead: 90% (225 points)

---

## 💡 Tips for Interviewers

1. **Provide Access:** Give candidates the repository and time to set up
2. **Observe Process:** Watch how they debug and investigate
3. **Ask Follow-ups:** "What tool did you use to find that?"
4. **Check Tools:** Ensure they're using DevTools effectively
5. **Real Scenarios:** Have them test actual user flows
6. **Documentation:** Ask them to document their findings

---

**These questions test practical, hands-on skills that can only be demonstrated by actually working with the running application!**
