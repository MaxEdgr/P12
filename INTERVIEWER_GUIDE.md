# Interviewer's Quick Reference Guide

## 🎯 Quick Assessment Questions (Pick 5-7)

### Must-Ask Security Questions
1. **Q10/Q11** - Malicious code in userRoute.js and eval() usage
   - **Look for:** Awareness of security risks, understanding of code injection
   - **Good answer:** Identifies obfuscated code, explains eval() dangers, suggests removal

2. **Q13** - JWT security
   - **Look for:** Understanding of token storage, expiration, refresh tokens
   - **Good answer:** Mentions httpOnly cookies, token expiration, refresh token rotation

### Architecture Understanding
3. **Q1** - Project structure
   - **Look for:** Clear understanding of separation of concerns
   - **Good answer:** Explains components (UI), pages (routing), hooks (logic), store (state)

4. **Q2** - Recoil vs React Query
   - **Look for:** Understanding of different state management needs
   - **Good answer:** Recoil for UI state, React Query for server state/caching

### Frontend Skills
5. **Q20** - Recoil usage
   - **Look for:** Understanding of state management flow
   - **Good answer:** Explains atom updates trigger re-renders, component subscriptions

6. **Q22** - Custom hooks
   - **Look for:** Understanding of React patterns
   - **Good answer:** Reusability, separation of concerns, easier testing

### Backend Skills
7. **Q31** - Middleware chain
   - **Look for:** Understanding of Express middleware
   - **Good answer:** Explains order matters, each middleware transforms request/response

---

## 🔍 Answer Evaluation Criteria

### Excellent (5/5)
- ✅ Provides clear, accurate explanation
- ✅ Gives code examples
- ✅ Discusses edge cases
- ✅ Mentions security/performance implications
- ✅ Suggests improvements

### Good (4/5)
- ✅ Correct understanding
- ✅ Some code examples
- ✅ Basic edge case awareness
- ⚠️ Missing some considerations

### Satisfactory (3/5)
- ✅ Generally correct
- ⚠️ Lacks depth
- ⚠️ Few examples
- ⚠️ Misses important considerations

### Needs Improvement (2/5)
- ⚠️ Partially correct
- ❌ Significant gaps in understanding
- ❌ No examples
- ❌ Doesn't consider edge cases

### Poor (1/5)
- ❌ Incorrect understanding
- ❌ No examples
- ❌ Can't explain concepts
- ❌ No awareness of best practices

---

## 🚨 Critical Red Flags

### Security Ignorance
- Doesn't recognize malicious code
- Suggests using eval()
- No input validation awareness
- Ignores SQL injection risks

### Poor Code Practices
- Suggests global variables
- No error handling
- Hardcodes sensitive data
- No consideration of scalability

### Lack of Understanding
- Can't explain own code
- Doesn't understand async/await
- Confuses frontend/backend concepts
- No awareness of performance implications

---

## 💡 Sample Good Answers

### Q10: Security Issue in userRoute.js
**Good Answer:**
"This is heavily obfuscated JavaScript code that appears to be malicious. It's using string obfuscation and dynamic code execution patterns commonly seen in malware. The code should be immediately removed. It could be:
- Data exfiltration
- Remote code execution
- Backdoor installation

I would:
1. Remove the code immediately
2. Audit the entire codebase for similar issues
3. Check git history to see when it was added
4. Review all dependencies for vulnerabilities
5. Implement code review processes to prevent this"

### Q2: Recoil vs React Query
**Good Answer:**
"Recoil is used for client-side UI state management - things like modal open/close states, form inputs, selected tabs. React Query is used for server state - API data, caching, background refetching, optimistic updates.

Recoil manages:
- `gamerInfoAtom` - UI state
- `collabListModalAtom` - Modal visibility

React Query manages:
- API responses from `/api/gamer/info`
- Caching of Steam game data
- Automatic refetching on window focus

They serve different purposes and complement each other well."

### Q31: Middleware Chain
**Good Answer:**
"In Express, middleware executes in order. Looking at app.js:
1. `express.json()` - Parses JSON request bodies
2. `cookieParser()` - Parses cookies
3. `bodyParser.urlencoded()` - Parses URL-encoded bodies
4. `fileUpload()` - Handles file uploads
5. Routes - Match and execute route handlers

Each middleware can:
- Modify req/res objects
- Call next() to continue
- Send response to end chain
- Throw errors

Order matters - if you need cookies parsed before routes, cookieParser must come before routes."

---

## 📋 Question Selection by Role

### Frontend Developer Focus
- Q1, Q2, Q20-Q30, Q42-Q44, Q63-Q65, Q73-Q75, Q83-Q85

### Backend Developer Focus
- Q3, Q31-Q41, Q53-Q59, Q66-Q69, Q76-Q79, Q86-Q89

### Full-Stack Developer
- Mix of all categories, emphasis on Q1-Q3, Q10-Q11, Q13, Q20, Q31, Q42

### Senior/Lead Developer
- Focus on Advanced questions: Q7-Q9, Q17-Q19, Q27-Q30, Q38-Q41, Q49-Q52, Q70-Q72, Q80-Q82, Q90-Q92, Q97-Q100

### Security Specialist
- All security questions (Q10-Q19) plus Q66, Q70, Q90-Q92

---

## 🎤 Follow-Up Questions

After each answer, consider asking:

1. **"Can you show me code for that?"**
   - Tests practical coding ability

2. **"What are the trade-offs?"**
   - Tests critical thinking

3. **"How would you test this?"**
   - Tests testing mindset

4. **"What could go wrong?"**
   - Tests edge case awareness

5. **"How would you improve this?"**
   - Tests optimization thinking

---

## ⏱️ Time Management

### 30-Minute Quick Test
- 2-3 Beginner (2 min each)
- 3-4 Intermediate (4 min each)
- 1 Advanced (6 min)
- **Total: ~30 minutes**

### 60-Minute Standard Test
- 3-4 Beginner (2 min each)
- 5-6 Intermediate (5 min each)
- 2-3 Advanced (8 min each)
- **Total: ~60 minutes**

### 120-Minute Comprehensive
- 5 Beginner (2 min each)
- 8 Intermediate (6 min each)
- 5 Advanced (10 min each)
- **Total: ~120 minutes**

---

## 📊 Scoring Rubric

### Overall Score Calculation
```
Score = (Beginner × 1) + (Intermediate × 2) + (Advanced × 3)
```

### Passing Thresholds
- **Junior Developer:** 40% (8-10 points)
- **Mid-Level Developer:** 60% (12-15 points)
- **Senior Developer:** 75% (15-19 points)
- **Lead Developer:** 85% (17-21 points)

### Category-Specific Thresholds
- **Security:** Must score 80%+ (critical)
- **Architecture:** 70%+ for senior roles
- **Code Quality:** 65%+ for all roles

---

## 🎯 Role-Specific Focus Areas

### Junior Frontend Developer
- React basics (Q20-Q22)
- Component structure (Q1)
- Basic security awareness (Q10-Q12)

### Mid-Level Full-Stack
- Architecture understanding (Q1-Q6)
- Security best practices (Q10-Q16)
- Performance basics (Q73-Q75)

### Senior Developer
- System design (Q7-Q9, Q97-Q100)
- Advanced security (Q17-Q19)
- Performance optimization (Q80-Q82)
- Code quality leadership (Q70-Q72)

---

## 🔄 Interview Flow Recommendations

### Opening (5 min)
1. Brief project overview
2. Ask candidate to explore codebase
3. "What do you notice first?"

### Main Assessment (varies)
1. Start with architecture (Q1-Q3)
2. Security questions (Q10-Q11) - critical
3. Role-specific questions
4. Problem-solving scenarios

### Closing (5 min)
1. "What would you improve?"
2. "Any questions about the codebase?"
3. "What challenges do you see?"

---

## 📝 Notes Template

```
Candidate: _______________
Date: _______________
Role: _______________

Questions Asked:
1. Q__ - Score: __/5 - Notes: _______________
2. Q__ - Score: __/5 - Notes: _______________
...

Total Score: __/__
Category Breakdown:
- Architecture: __/__
- Security: __/__
- Frontend: __/__
- Backend: __/__
...

Strengths:
- _______________
- _______________

Weaknesses:
- _______________
- _______________

Recommendation: [ ] Hire [ ] Maybe [ ] Pass
```

---

## 🎓 Training Resources for Candidates

If candidates struggle, you can recommend:

1. **Security:** OWASP Top 10, Node.js Security Best Practices
2. **React:** React documentation, React Query docs
3. **Web3:** Ethereum docs, Wagmi documentation
4. **Architecture:** Clean Architecture, Design Patterns
5. **Performance:** Web.dev, Next.js optimization guide

---

**Remember:** The goal is to assess problem-solving ability and technical knowledge, not to trick candidates. Use these questions as conversation starters to understand their thought process and experience level.
