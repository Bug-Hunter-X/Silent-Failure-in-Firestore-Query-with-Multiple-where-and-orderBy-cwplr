# Silent Failure in Firestore Query with Multiple where and orderBy

This repository demonstrates a subtle bug encountered when using Firebase Firestore queries with multiple `where` clauses combined with an `orderBy` clause.  The query fails silently, returning no data without any clear error messages.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file demonstrates the corrected approach.

**Problem:** Incorrectly ordered `where` clauses with composite indexes can lead to unexpected behavior.  Firestore might not be able to optimize the query efficiently. 

**Solution:** Ensure that the ordering of the `where` clauses aligns with the `orderBy` clause. This often involves creating composite indexes in the Firestore console.