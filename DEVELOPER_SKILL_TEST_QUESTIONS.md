# P12 Airdrop Project - Developer Skill Test Questions

## Instructions for Interviewers
This document contains questions organized by category and difficulty level. Use these to assess candidates' skills across different aspects of full-stack Web3 development.

---

## 📋 Table of Contents
1. [Architecture & Design](#architecture--design)
2. [Security](#security)
3. [Frontend (React/Next.js)](#frontend-reactnextjs)
4. [Backend (Node.js/Express)](#backend-nodejsexpress)
5. [Web3 & Blockchain](#web3--blockchain)
6. [Database & Data Modeling](#database--data-modeling)
7. [Code Quality & Best Practices](#code-quality--best-practices)
8. [Performance Optimization](#performance-optimization)
9. [Debugging & Problem Solving](#debugging--problem-solving)
10. [System Design](#system-design)

---

## 🏗️ Architecture & Design

### Beginner
**Q1:** Looking at the project structure, explain the difference between the `components/`, `pages/`, `hooks/`, and `store/` directories in the frontend. What goes where and why?

**Q2:** Why does this project use both Recoil and React Query? What problem does each solve?

**Q3:** The backend has routes, controllers, and models. Explain the flow of a request from route → controller → model.

### Intermediate
**Q4:** This project mixes e-commerce models (Product, Order, Payment) with airdrop functionality. How would you refactor this to better separate concerns?

**Q5:** The frontend uses both `lib/api.ts` and `lib/api-nest.ts`. What's the purpose of having two API clients? How would you consolidate them?

**Q6:** Explain the authentication flow in this application. How does Steam OAuth integrate with Web3 wallet authentication?

### Advanced
**Q7:** Design a microservices architecture for this project. Which services would you separate and how would they communicate?

**Q8:** How would you implement a caching strategy for frequently accessed data like gamer rankings and developer game lists?

**Q9:** The project supports multiple blockchain networks. Design a system to handle chain-specific logic and contract interactions.

---

## 🔒 Security

### Beginner
**Q10:** What security issues do you notice in `backend/routes/userRoute.js`? What should be done about it?

**Q11:** In `backend/controllers/userController.js` line 203, there's an `eval()` statement. Why is this dangerous and how would you fix it?

**Q12:** The database connection is commented out in `server.js`. What impact does this have and how would you properly configure it?

### Intermediate
**Q13:** Review the JWT token implementation. What security measures are in place? What additional measures would you add?

**Q14:** The Steam OAuth flow uses secret tokens stored in localStorage. What are the security implications and how would you improve this?

**Q15:** How would you implement rate limiting to prevent API abuse? Which endpoints need it most?

**Q16:** The password hashing uses SHA-512 with custom salt generation. Is this secure? What would you recommend instead?

### Advanced
**Q17:** Design a comprehensive security audit checklist for this application. What areas need the most attention?

**Q18:** How would you implement Content Security Policy (CSP) headers to prevent XSS attacks?

**Q19:** The project handles sensitive user data (Steam profiles, wallet addresses). What data protection measures would you implement?

---

## ⚛️ Frontend (React/Next.js)

### Beginner
**Q20:** In `pages/gamer/index.tsx`, explain how the component uses Recoil atoms. What happens when `gamerInfoAtom` updates?

**Q21:** Why does `pages/_app.tsx` wrap the app with `QueryClientProvider`? What does React Query provide?

**Q22:** Looking at `hooks/useSteamSignIn.ts`, explain the custom hook pattern. What benefits does it provide?

### Intermediate
**Q23:** The `useSteamSignIn` hook uses `useEvent` to listen to storage events. Explain this pattern and potential issues.

**Q24:** In `components/gamer/`, there are multiple components. How would you optimize the component tree to reduce re-renders?

**Q25:** The project uses both `useMemo` and `useCallback`. When should each be used? Find examples in the codebase.

**Q26:** How would you implement error boundaries to catch React errors gracefully?

### Advanced
**Q27:** The project loads badge images dynamically. How would you implement image optimization and lazy loading?

**Q28:** Design a state management solution that could replace Recoil. What are the trade-offs?

**Q29:** The homepage shows rankings that update in real-time. How would you implement WebSocket connections for live updates?

**Q30:** How would you implement Server-Side Rendering (SSR) for SEO-critical pages like the homepage?

---

## 🖥️ Backend (Node.js/Express)

### Beginner
**Q31:** Explain the middleware chain in `backend/app.js`. What does each middleware do?

**Q32:** In `backend/controllers/userController.js`, what is `asyncErrorHandler`? Why is it needed?

**Q33:** The project uses Mongoose for database operations. Explain the difference between `find()`, `findOne()`, and `findById()`.

### Intermediate
**Q34:** Review `backend/models/User.js`. The password hashing happens in a pre-save hook. Explain this pattern and its benefits.

**Q35:** How would you implement pagination for the user list endpoint? Show the code.

**Q36:** The project uses Cloudinary for image storage. How would you handle image upload validation and error handling?

**Q37:** Design an API versioning strategy. How would you migrate from `/api/v1` to `/api/v2`?

### Advanced
**Q38:** How would you implement a job queue system for processing Steam API calls asynchronously?

**Q39:** The Steam OAuth callback needs to handle mobile and desktop differently. Design a robust solution.

**Q40:** How would you implement request logging and monitoring? What metrics would you track?

**Q41:** Design a caching layer using Redis for frequently accessed data. Which endpoints would benefit most?

---

## ⛓️ Web3 & Blockchain

### Beginner
**Q42:** Explain how wallet connection works in this project. What libraries are used and why?

**Q43:** Looking at `connectors/index.ts`, what is the purpose of configuring multiple wallet connectors?

**Q44:** What is a Soul-Bound NFT? How does it differ from a regular NFT?

### Intermediate
**Q45:** The project supports multiple chains (BSC, Polygon, Linea). How would you handle chain switching and ensure the correct contracts are called?

**Q46:** Explain the SIWE (Sign-In with Ethereum) flow. How does it provide authentication?

**Q47:** How would you handle failed transactions? Design an error handling and retry mechanism.

**Q48:** The project uses ABIs from `abis/` directory. What are ABIs and why are they needed?

### Advanced
**Q49:** Design a system to batch multiple NFT claims into a single transaction to save gas.

**Q50:** How would you implement a multi-sig wallet for admin operations?

**Q51:** The project needs to verify on-chain NFT ownership. Design a verification system.

**Q52:** How would you handle network congestion and high gas fees? Design a queuing system.

---

## 🗄️ Database & Data Modeling

### Beginner
**Q53:** Review `backend/models/AdminBank.js`. What is the purpose of the `isVerified` field being a Date instead of Boolean?

**Q54:** Explain the relationship between User and Address models. How is it defined in Mongoose?

**Q55:** What are Mongoose timestamps? How are they used in this project?

### Intermediate
**Q56:** The Product model has many optional fields. How would you design a more normalized schema?

**Q57:** Design database indexes for the User model. Which fields should be indexed and why?

**Q58:** How would you implement soft deletes? The Product model has `isDeleted` - how would you query active products?

**Q59:** The project needs to store Steam game data. Design a schema that supports efficient queries for rankings.

### Advanced
**Q60:** Design a database migration strategy. How would you handle schema changes in production?

**Q61:** How would you implement database sharding for scaling? Which collections would you shard?

**Q62:** Design a data archiving strategy for old user data and completed airdrops.

---

## ✨ Code Quality & Best Practices

### Beginner
**Q63:** The project mixes `.js` and `.ts/.tsx` files. What are the benefits of migrating everything to TypeScript?

**Q64:** Review `lib/api.ts`. How would you add TypeScript types to improve type safety?

**Q65:** Find code duplication in the project. How would you refactor it?

### Intermediate
**Q66:** The error handling is inconsistent across controllers. Design a standardized error handling pattern.

**Q67:** How would you implement input validation? Show an example using a validation library.

**Q68:** The project lacks unit tests. Write a test for the `registerUser` controller function.

**Q69:** How would you implement logging? What information should be logged and what should be excluded?

### Advanced
**Q70:** Design a code review checklist for this project. What patterns should reviewers look for?

**Q71:** How would you implement feature flags for gradual rollouts?

**Q72:** Design a CI/CD pipeline for this project. What stages would it include?

---

## 🚀 Performance Optimization

### Beginner
**Q73:** The homepage loads multiple API calls. How would you optimize this using React Query?

**Q74:** Large images are loaded without optimization. How would you implement Next.js Image optimization?

**Q75:** The project doesn't use code splitting. Which routes would benefit from lazy loading?

### Intermediate
**Q76:** The rankings page loads all users. How would you implement virtual scrolling for large lists?

**Q77:** API responses don't have compression. How would you add gzip compression?

**Q78:** Design a caching strategy for Steam API calls to reduce external API usage.

**Q79:** The database queries don't use projection. How would you optimize queries to fetch only needed fields?

### Advanced
**Q80:** How would you implement a CDN strategy for static assets?

**Q81:** Design a GraphQL API to replace REST endpoints. What are the benefits and trade-offs?

**Q82:** The project needs to handle 10,000+ concurrent users. What optimizations would you implement?

---

## 🐛 Debugging & Problem Solving

### Beginner
**Q83:** A user reports they can't connect their wallet. What steps would you take to debug this?

**Q84:** The Steam OAuth flow works on desktop but not mobile. What could be the issue?

**Q85:** Users are seeing stale data after updating their profile. What's likely causing this?

### Intermediate
**Q86:** The database connection fails intermittently. How would you diagnose and fix this?

**Q87:** NFT claims are failing for some users but not others. How would you debug this?

**Q88:** The rankings page is slow. How would you profile and optimize it?

**Q89:** API calls are timing out. What could be causing this and how would you fix it?

### Advanced
**Q90:** Users report that their token balances are incorrect. Design a debugging strategy.

**Q91:** The application crashes under load. How would you identify the bottleneck?

**Q92:** Design a monitoring and alerting system for production issues.

---

## 🎯 System Design

### Intermediate
**Q93:** Design a notification system to alert users when their NFT is ready to claim.

**Q94:** How would you implement a referral tracking system that prevents fraud?

**Q95:** Design an admin dashboard for managing users, verifying games, and monitoring airdrops.

**Q96:** How would you implement A/B testing for the airdrop claim flow?

### Advanced
**Q97:** Design a scalable architecture to handle 1 million users claiming NFTs simultaneously.

**Q98:** How would you implement a multi-region deployment strategy?

**Q99:** Design a disaster recovery plan. What are the critical systems and how would you back them up?

**Q100:** The project needs to integrate with 10+ different blockchain networks. Design an abstraction layer.

---

## 📊 Scoring Guide

### By Difficulty Level
- **Beginner (Q1-Q33, Q42-Q55, Q63-Q75, Q83-Q85):** 1 point each
- **Intermediate (Q4-Q9, Q13-Q16, Q23-Q29, Q34-Q40, Q45-Q48, Q56-Q59, Q66-Q69, Q76-Q79, Q86-Q89, Q93-Q96):** 2 points each
- **Advanced (Q7-Q9, Q17-Q19, Q27-Q30, Q38-Q41, Q49-Q52, Q60-Q62, Q70-Q72, Q80-Q82, Q90-Q92, Q97-Q100):** 3 points each

### By Category
- Architecture: 15 questions (25 points)
- Security: 10 questions (20 points)
- Frontend: 11 questions (20 points)
- Backend: 11 questions (20 points)
- Web3: 11 questions (20 points)
- Database: 10 questions (18 points)
- Code Quality: 10 questions (18 points)
- Performance: 10 questions (18 points)
- Debugging: 10 questions (18 points)
- System Design: 8 questions (18 points)

**Total: 100 questions, 195 points**

---

## 🎯 Recommended Test Structure

### Quick Assessment (30 minutes)
- 5 Beginner questions (1 each)
- 5 Intermediate questions (2 each)
- 2 Advanced questions (3 each)
- **Total: 21 points**

### Standard Assessment (60 minutes)
- 10 Beginner questions (1 each)
- 10 Intermediate questions (2 each)
- 5 Advanced questions (3 each)
- **Total: 45 points**

### Comprehensive Assessment (120 minutes)
- 15 Beginner questions (1 each)
- 15 Intermediate questions (2 each)
- 10 Advanced questions (3 each)
- **Total: 75 points**

---

## 💡 Interview Tips

1. **Start with architecture questions** to assess overall understanding
2. **Security questions are critical** - prioritize these
3. **Ask follow-up questions** - "How would you implement that?"
4. **Request code examples** for intermediate/advanced questions
5. **Discuss trade-offs** - there's rarely one "right" answer
6. **Assess problem-solving approach** - how they think matters more than exact answers

---

## 📝 Answer Key Guidelines

### Good Answers Should Include:
- Clear explanation of concepts
- Code examples when appropriate
- Consideration of edge cases
- Discussion of trade-offs
- Security considerations
- Performance implications

### Red Flags:
- No awareness of security issues
- Can't explain their own code
- No consideration of edge cases
- Ignores best practices
- Can't discuss trade-offs

---

**Good luck with your developer assessments!** 🚀
