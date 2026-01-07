# Quick Reference Cheat Sheet

## 🚨 CRITICAL SECURITY QUESTIONS (Must Ask)

### Q10: Malicious Code in userRoute.js
**What to look for:**
- ✅ Recognizes obfuscated/malicious code
- ✅ Understands security risk
- ✅ Suggests immediate removal

**Key Points:**
- Line 26+ contains heavily obfuscated JavaScript
- Could be data exfiltration or backdoor
- Should be removed and codebase audited

**Red Flag:** Doesn't recognize it as malicious

---

### Q11: eval() Usage in userController.js
**What to look for:**
- ✅ Understands eval() is dangerous
- ✅ Knows it executes arbitrary code
- ✅ Suggests safe alternatives

**Key Points:**
- Line 203: `eval(response.data.cookie)`
- Executes external API response as code
- High security risk - code injection possible

**Red Flag:** Says eval() is fine or doesn't know the risk

---

## 🏗️ ARCHITECTURE ESSENTIALS

### Q1: Project Structure
**Expected Answer:**
- `components/` - Reusable UI components
- `pages/` - Next.js routes/pages
- `hooks/` - Custom React hooks (reusable logic)
- `store/` - Recoil state management (global state)

**Red Flag:** Can't explain separation of concerns

---

### Q2: Recoil vs React Query
**Expected Answer:**
- **Recoil:** Client-side UI state (modals, form inputs, selected items)
- **React Query:** Server state (API data, caching, refetching)

**Key Insight:** They solve different problems and complement each other

---

## ⚛️ FRONTEND KEY CONCEPTS

### Q20: Recoil Atoms
**Expected Answer:**
- Atoms are state containers
- Components subscribe to atoms
- When atom updates, subscribed components re-render
- Example: `gamerInfoAtom` updates → gamer page re-renders

---

### Q22: Custom Hooks Pattern
**Expected Answer:**
- Encapsulates reusable logic
- Easier to test
- Better code organization
- Example: `useSteamSignIn` handles Steam OAuth flow

---

## 🖥️ BACKEND KEY CONCEPTS

### Q31: Middleware Chain
**Expected Answer:**
- Executes in order
- Each can modify req/res
- Must call `next()` to continue
- Order matters!

**Flow:** json() → cookieParser() → bodyParser() → fileUpload() → routes

---

### Q34: Pre-Save Hooks
**Expected Answer:**
- Runs before document save
- Used for password hashing
- Automatic transformation
- Ensures data consistency

---

## ⛓️ WEB3 ESSENTIALS

### Q42: Wallet Connection
**Expected Answer:**
- Uses Wagmi library
- Multiple connectors (MetaMask, WalletConnect, etc.)
- Handles chain switching
- Provides hooks like `useAccount()`

---

### Q45: Multi-Chain Support
**Expected Answer:**
- Configure chains in `connectors/index.ts`
- Use `useNetwork()` to detect current chain
- Switch chains with `switchNetwork()`
- Different contracts per chain

---

## 🗄️ DATABASE BASICS

### Q53: isVerified as Date
**Expected Answer:**
- Stores verification timestamp
- `null` = not verified
- Date = verified at that time
- More informative than boolean

---

### Q57: Database Indexes
**Expected Answer:**
- Index frequently queried fields
- User: `email`, `userID`, `walletAddress`
- Speeds up queries
- Trade-off: slower writes

---

## 🔍 CODE QUALITY

### Q63: TypeScript Migration
**Expected Answer:**
- Type safety
- Better IDE support
- Catch errors at compile time
- Easier refactoring

**Red Flag:** Doesn't see value in TypeScript

---

### Q66: Error Handling Pattern
**Expected Answer:**
- Centralized error handler
- Consistent error format
- Proper HTTP status codes
- Logging for debugging

---

## 🚀 PERFORMANCE

### Q73: API Call Optimization
**Expected Answer:**
- Use React Query caching
- Parallel queries with `useQueries()`
- Stale-while-revalidate pattern
- Reduce unnecessary refetches

---

### Q75: Code Splitting
**Expected Answer:**
- Lazy load routes
- Dynamic imports
- Split by route
- Reduce initial bundle size

---

## 🐛 DEBUGGING APPROACH

### Q83: Wallet Connection Issue
**Expected Answer:**
1. Check browser console
2. Verify wallet extension installed
3. Check network connection
4. Verify chain compatibility
5. Check connector configuration

**Good Answer:** Systematic debugging approach

---

## 📊 SCORING QUICK REFERENCE

### Points System
- Beginner: 1 point
- Intermediate: 2 points  
- Advanced: 3 points

### Passing Scores
- Junior: 40% (8-10 points)
- Mid: 60% (12-15 points)
- Senior: 75% (15-19 points)
- Lead: 85% (17-21 points)

---

## 🎯 TOP 10 MUST-ASK QUESTIONS

1. **Q10** - Security: Malicious code (CRITICAL)
2. **Q11** - Security: eval() usage (CRITICAL)
3. **Q1** - Architecture: Project structure
4. **Q2** - Architecture: Recoil vs React Query
5. **Q20** - Frontend: Recoil usage
6. **Q31** - Backend: Middleware chain
7. **Q42** - Web3: Wallet connection
8. **Q63** - Code Quality: TypeScript benefits
9. **Q73** - Performance: API optimization
10. **Q83** - Debugging: Problem-solving approach

---

## 🚩 RED FLAGS CHECKLIST

- [ ] Doesn't recognize security issues
- [ ] Can't explain own code
- [ ] No error handling awareness
- [ ] Ignores best practices
- [ ] Can't discuss trade-offs
- [ ] No testing mindset
- [ ] Doesn't consider edge cases
- [ ] Poor code organization ideas
- [ ] No performance awareness
- [ ] Can't debug systematically

---

## ✅ GREEN FLAGS CHECKLIST

- [ ] Immediately spots security issues
- [ ] Explains concepts clearly
- [ ] Provides code examples
- [ ] Discusses trade-offs
- [ ] Considers edge cases
- [ ] Suggests improvements
- [ ] Asks clarifying questions
- [ ] Shows testing mindset
- [ ] Performance-conscious
- [ ] Systematic debugging approach

---

## 💬 GOOD FOLLOW-UP QUESTIONS

After any answer, ask:
1. "Can you show me code for that?"
2. "What are the trade-offs?"
3. "How would you test this?"
4. "What could go wrong?"
5. "How would you improve this?"

---

## 📝 QUICK EVALUATION

### Excellent (5/5)
- Clear explanation + code + edge cases + improvements

### Good (4/5)
- Correct + some examples + basic awareness

### Satisfactory (3/5)
- Generally correct but lacks depth

### Needs Work (2/5)
- Partially correct, significant gaps

### Poor (1/5)
- Incorrect or can't explain

---

## 🎤 INTERVIEW FLOW

1. **Warm-up (5 min):** "What do you notice about this codebase?"
2. **Core Assessment (varies):** Architecture → Security → Role-specific
3. **Wrap-up (5 min):** "What would you improve?"

---

## 🔑 KEY INSIGHTS TO LOOK FOR

### Problem-Solving Approach
- ✅ Systematic debugging
- ✅ Asks clarifying questions
- ✅ Breaks down complex problems
- ✅ Considers multiple solutions

### Technical Depth
- ✅ Understands "why" not just "how"
- ✅ Discusses trade-offs
- ✅ Considers edge cases
- ✅ Aware of best practices

### Communication
- ✅ Explains clearly
- ✅ Uses examples
- ✅ Asks questions
- ✅ Admits when unsure

---

**Remember:** The goal is to understand their thought process and problem-solving ability, not to trick them!
