# Writing good PR descriptions



A PR description is a public record of **what** change is being made and **why**
it was made. It will become a permanent part of our version control history, and
will possibly be read by people other than your reviewers over the
years.

Future developers will search for your PR based on its description. Someone in
the future might be looking for your change because of a faint memory of its
relevance but without the specifics handy. If all the important information is
in the code and not the description, it's going to be a lot harder for them to
locate your PR.

## First Line {#firstline}

*   Short summary of what is being done.
*   Complete sentence, written as though it was an order.
*   Follow by empty line.

The **first line** of a PR description should be a short summary of
*specifically* **what** *is being done by the PR*, followed by a blank line.
This is what appears in version control history summaries, so it should be
informative enough that future code searchers don't have to read your PR or its
whole description to understand what your PR actually *did* or how it differs
from other PRs. That is, the first line should stand alone, allowing readers to
skim through code history much faster.

Try to keep your first line short, focused, and to the point. The clarity and
utility to the reader should be the top concern.

By tradition, the first line of a PR description is a complete sentence, written
as though it were an order (an imperative sentence). For example, say
\"**Delete** the FizzBuzz RPC and **replace** it with the new system." instead
of \"**Deleting** the FizzBuzz RPC and **replacing** it with the new system."
You don't have to write the rest of the description as an imperative sentence,
though.

## Body is Informative {#informative}

The [first line](#firstline) should be a short, focused summary, while the rest
of the description should fill in the details and include any supplemental
information a reader needs to understand the changes. It might
include a brief description of the problem that's being solved, and why this is
the best approach. If there are any shortcomings to the approach, they should be
mentioned. If relevant, include background information such as bug numbers,
benchmark results, and links to design documents.

If you include links to external resources consider that they may not be visible
to future readers due to access restrictions or retention policies. Where
possible include enough context for reviewers and future readers to understand
the PR.

Even small PRs deserve a little attention to detail. Put the PR in context.

## Bad PR Descriptions {#bad}

"Fix bug" is an inadequate PR description. What bug? What did you do to fix it?
Other similarly bad descriptions include:

-   "Moving code from A to B."
-   "Phase 1."
-   "kill weird URLs."

Although short, they do not provide enough useful information.

## Good PR Descriptions {#good}

Here are some examples of good descriptions.

### Functionality change

Example:

> Remove size limit on email bodies.
>
> The email bodies have changed to use html, which resulted in much larger message sizes.
> The limit was imposed by the database column size that I increased to nvarchar(max)
> to cater for all message size scenarios.

The first few words describe what the PR actually does. The rest of the
description talks about the problem being solved, why this is a good solution,
and a bit more information about the specific implementation.

### Refactoring

Example:

> Add a JobScheduler with an Email queue and use it to send all emails.
>
> The JobScheduler.Email_DoJob sends the email and writes a log.
> All SendMail functions are replaced with JobScheduler.Email_DoJob to simplify the code
> and provide a more robust notification infrastructure. The queue handles errors
> and provides protection against data loss if the server goes down.

The first line describes what the PR does and how this is a change from the
past. The rest of the description talks about the specific implementation and the
context of the PR. It also explains *why* this change is being made.

### Small PR that needs some context

Example:

> Change Email read protocol to IMAP.
>
> The customer's email infrastructure is discontinuing support for POP3  
> on 31 December 2023. 

The first sentence describes what's actually being done. The rest of the
description explains *why* the change is being made and gives the reviewer a lot
of context.

## Review the description before submitting the PR

PRs can undergo significant change during review. It can be worthwhile to review
a PR description before submitting the PR, to ensure that the description still
reflects what the PR does.

Next: [Small PRs](small-prs.md)
