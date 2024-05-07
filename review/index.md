
## Introduction {#intro}

A code review is a process where someone other than the author(s) of a piece of
code examines that code.

We use code review to maintain the quality of our code and products.

This page is an overview of our code review process. There are two other documents that are a part of this guide:

-   **[How To Do A Code Review](reviewer/index.md)**: A detailed guide for code
    reviewers.
-   **[The PR Author's Guide](developer/index.md)**: A detailed guide for
    developers whose PRs are going through review.

## What Do Code Reviewers Look For? {#look_for}

Code reviews should look at:

-   **Design**: Is the code well-designed and appropriate for your system?
-   **Functionality**: Does the code behave as the author likely intended? Is
    the way the code behaves good for its users?
-   **Complexity**: Could the code be made simpler? Would another developer be
    able to easily understand and use this code when they come across it in the
    future?
-   **Tests**: Does the code have correct and well-designed automated tests?
-   **Naming**: Did the developer choose clear names for functions, types, variables, etc.?
-   **Style**: Does the code follow our
    [style guides](../styleguide/linx-style.md)?
-   **Documentation**: Did the developer also update relevant documentation?

See **[How To Do A Code Review](reviewer/index.md)** for more information.

### Picking the Best Reviewers {#best_reviewers}

In general, you want to find the *best* reviewers you can who are capable of
responding to your review within a reasonable period of time.

The best reviewer is the person who will be able to give you the most thorough
and correct review for the piece of code you are writing. This usually means the
owner(s) of the code or the senior on the project, who may or may not be the ideal reviewer of all the items affected by the PR. Sometimes this means asking different people to review different parts of the PR.

### In-Person Reviews (and Pair Programming) {#in_person}

If you pair-programmed a piece of code with somebody who was qualified to do a
good code review on it, then that code is considered reviewed.

You can also do in-person code reviews where the reviewer asks questions and the
developer of the change speaks only when spoken to.

## See Also {#seealso}

-   [How To Do A Code Review](reviewer/index.md): A detailed guide for code
    reviewers.
-   [The PR Author's Guide](developer/index.md): A detailed guide for developers
    whose PRs are going through review.

## Terminology

There is some terminology used in some of these documents, which
we clarify here:

*   **PR**: Stands for "pull-request", which means one self-contained change that
    has been submitted to version control or which is undergoing code review.
    Other organizations might call this a "change", "patch", or "changelist".
*   **LGTM**: Means "Looks Good to Me". It is what a code reviewer says when
    approving a PR.