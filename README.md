# AngularFireBugfix

Bug Fix for rxfire
Issue
When integrating with the latest version of rxfire, we encountered a TypeScript error related to the type definition in rxfire/firestore/lite/interfaces.d.ts. The specific error message is:

typescript

Error: node_modules/rxfire/firestore/lite/interfaces.d.ts:8:29 - error TS2314: Generic type 'AggregateQuerySnapshot<T>' requires 1 type argument(s).

8 export type CountSnapshot = lite.AggregateQuerySnapshot<{
                              ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
9     count: lite.AggregateField<number>;
  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
10 }, any, DocumentData>;
Solution
To fix the issue, we recommend downgrading rxfire to version 6.0.3. This version does not have the aforementioned TypeScript error.

Steps to Apply the Fix
In your project directory, run the following command:
bash

npm install rxfire@6.0.3
Ensure that the package has been updated in your package.json:
json

"dependencies": {
    ...
    "rxfire": "^6.0.3",
    ...
}
Rebuild or restart your project to ensure the changes are applied.
Additional Notes
If you've applied other workarounds, such as module augmentation, consider reverting them after downgrading rxfire.
We've reported this issue to the rxfire maintainers. Keep an eye on future releases for a potential fix.
Remember to always check compatibility and known issues when updating libraries in your project.
You can add this BUG_FIX_README.md to your repository and reference it in your main README.md or in the issues section as needed. This will help other contributors or users understand the issue and the recommended fix.
