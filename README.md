# Skytable RFCs

A collection of the RFCs for the [Skytable Project](https://github.com/skytable/skytable). RFCs are huge changes made to the Skytable database such as the introduction of a new protocol version, change in any of the project's policies and so on.

## Feature requests

Please note that **RFCs are not feature requests!** To **create a feature request, [open an issue here](https://github.com/skytable/skytable/issues/new?assignees=&labels=C-enhancement&template=feature_request.md&title=Feature%3A+)**. Any feature requests created here will be transferred to the [primary repository](https://github.com/skytable/skytable).

## Creating an RFC

Use the [0000-template.md](./0000-template.md) file as the base and fill in the placeholders in the appropriate sections.

## Procedure

The RFC procedure is highlighted below:

1. You fork the repo, add your RFC, sign the FLA and submit a PR
2. Change the `0000` in the RFC number to the issue number
3. The PR is your "RFC Proposal" and this proposal enters the _Initial Comment Period (ICP)_. The ICP under normal circumstances lasts up to a maximum of 15 days unless any significant objection is raised.
   - During this period any early objections or suggestions are made.
   - You can continue to update your RFC as and when required, to adhere to suggestions for example.
   - **Do not squash your commits.** We want every change to be present for sake of posterity.
   - Build consensus and integrate feedback during this period
   - Any offline discussions should be updated on the pull request itself in the form of comments
   - An admin can motion for _tabling_ or _closing_ the RFC. In that case, no further discussion will take place at this time and the pull request will be closed. If any concerns arise in the future, the RFC will be re-opened and the ICP will begin once again.
     > An RFC may not be tabled during the ICP, but may be tabled during the FCP (described below).
4. After the ICP completes, one of the admins will motion for the _Final Comment Period (FCP)_. This period under normal circumstances lasts up to a maximum of 7 days unless any significant objection is raised.
   - As soon as the FCP is entered, one of the admins will add a disposition for the RFC: accept, close or table.
   - No major changes other than brief corrections can be made during the FCP
   - This period is intended for final agreements between the author, the team and other participants in the RFC.
   - At the end of the FCP, an admin will add the _final disposition_ for the RFC
5. Once the FCP completes, the final disposition is applied and the RFC is closed. If the RFC was accepted, then implementation PRs and tracking issues will be used to track and implement the requisite items in [the primary repo](https://github.com/skytable/skytable).

## License

    Copyright (C) 2021 Sayan Nandan.

    Permission is granted to copy, distribute and/or modify the code examples in the documents
    under the terms of the GNU Affero General Public License, Version 3.0
    or any later version published by the Free Software Foundation.
    A copy of the license is included in the "LICENSE-AGPL.md" file in this directory or can be
    found at this URL: https://www.gnu.org/licenses/agpl-3.0.en.html

    Permission is granted to copy, distribute and/or modify the documents excluding their code examples
    under the terms of the GNU Free Documentation License, Version 1.3
    or any later version published by the Free Software Foundation;
    with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
    A copy of the license is included in the "LICENSE-GFDL.md" file in this directory or can
    be found at this URL: https://www.gnu.org/licenses/fdl-1.3.en.html

Any code examples in an RFC are distributed under the AGPL-3.0 License, the full text for which can be
found in the [LICENSE-AGPL.md](./LICENSE-AGPL.md) file in this directory or at this URL: https://www.gnu.org/licenses/agpl-3.0.html.
The content of an RFC other than any code examples is distributed under the GFDL-1.3 License, the full
text for which can be found in the [LICENSE-GFDL.md](./LICENSE-GFDL.md) file in this directory or at this URL: https://www.gnu.org/licenses/fdl-1.3.en.html.
