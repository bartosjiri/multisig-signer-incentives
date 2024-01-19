# Document

---

🚧 Below is the raw form of the main document. We are currently also working on a fully stylized PDF version 🚧

---

# Introduction to multisignature wallets

### _A comprehensive handbook for web3 projects and individuals_

Author: [Jiri Bartos](https://twitter.com/bartosjiri_)

Editors: [Mosadoluwa Fasasi](https://twitter.com/mofasasi), [Camille Delfin](https://twitter.com/caramelcamel_)

## Introduction

Multisignature wallets are a popular tool among various web3 projects for the management of shared funds and assets, providing enhanced decentralization, security, and other benefits. Being based on smart contracts, multisigs offer high customizability, which projects adapt to their specific needs. However, information and resources on related topics are scattered across the web, and taking inspiration from existing projects is not straightforward, as setups are often buried in long forum threads, governance proposals, and Discord channels.

This document aims to establish an educational foundation on the topic of multisignature wallets; providing an introduction to base components of multisigs and supporting it with examples from existing projects. With the information shared in the following pages, existing and emerging projects should be able to design configurations of their multisigs that fulfill their needs. Similarly, individuals taking part in the management of multisigs should gain an understanding of the responsibilities and risks stemming from their roles, becoming effective multisig operators.

### Notice

In the dynamic world of web3, taking any action demands caution and research. Follow the rule of “do your own research” (DYOR), a critical step in personal and collective security. Verify information from multiple sources emphasizing independent perspectives. Don’t solely rely on an apparent consensus; your personal opinion matters. The same applies to the information available in this document. Nonetheless, we believe it will provide a solid foundation for your further exploration.

### Research

The foundation for this document originates from a research project titled “How to responsibly incentivize multisig signers?”, an initiative to explore the approaches and methods of rewarding signers. However, as the data unfolded, it became apparent that this challenge is intertwined with other related topics, therefore, the findings are presented in a broader format to encompass them all. While this compilation does not hold a broad statistical validity, it effectively illustrates various options to set up a multisig.

To learn more about the research and its outcomes, visit [the project repository](https://github.com/bartosjiri/multisig-signer-incentives).

### Acknowledgements

The research has been generously supported by the [Safe Grants Program](https://grants.safe.global). Safe is a leading provider of the most trusted decentralized custody protocol and collective asset management platform. Explore its products and community at [safe.global](https://safe.global).

We would also like to thank each and every one of those who contributed to this research, either by sharing your experience through a survey, engaging in insightful conversations with us, or simply by publishing details about your project at easily accessible locations.

With all this support, we are able to assist existing and emerging projects in responsibly setting up and managing their multisignature wallets, and ultimately, safeguarding their assets without compromising their effective operations. Thank you!

### About Multisight

Multisight is an analytics tool for evaluating the response activity of multisignature wallets. Gain insight into the operations of your multisig, identify bottlenecks, effectively optimize your processes, and keep your signers accountable.

Inspect your multisig wallet with Multisight for free at [multisight.app](https://multisight.app).

## What is a multisig?

A multisignature wallet, commonly referred to as “multisig”, is a type of cryptocurrency wallet that typically requires two or more private keys to perform certain actions.

A crypto wallet is a digital tool that enables users to securely store, receive, and send various types of cryptocurrencies or tokens. It serves as a user interface for interacting with the blockchain, managing the private and public keys necessary for accessing and controlling digital assets. Crypto wallets, whether regular or multisignature, are represented by an address, a unique alphanumeric identifier derived from the public key.

Most multisigs are based on smart contracts, which implement all the necessary functionality. As there are many different smart contracts, and anyone has the freedom to develop their own, we will take a detailed look at only a few of the most typical features and components.

### Owners

The ownership of a multisignature wallet is distributed among user addresses associated with the wallet. These addresses, or crypto wallets, are called “owners” and together, they are in control of the multisig.

The initial assignment of owners into this role is done during the deployment of the multisig smart contract. Due to the flexible customization of multisig wallets, owners can be added or removed from the multisig during its regular operation. As in all other actions, this requires the confirmation threshold (or consensus) to be met by other signers.

### Signers and confirmation threshold

A “signer” is a term for a multisig owner who confirms pending actions by signing it with their private key.

For an action to be executable, it needs to reach a predefined threshold of confirmations from the pool of owners. Similar to the assignment of individual owners, this threshold can be specified on the initial deployment of the smart contract or at any time during the operation of the multisig.

The threshold can be any number of owners, from a single one to all of them. However, to fully utilize the benefits of multisignature wallets, some value in between this range is commonly preferred.

Individual confirmation signatures can be collected either off-chain or on-chain, depending on the implementation of the multisig. During an off-chain collection of the necessary threshold, signatures are collected by the multisig provider and sent to the blockchain together only during the action execution. On the contrary, on-chain multisig contracts can maintain the confirmation records in their on-chain state.

### Actions

Actions refer to any on-chain operation of the multisig, requiring the predefined threshold of confirmations. These include asset transfers, interaction with other smart contracts, or functions within the multisig contract itself, such as updates to the owners' pool and changes in the confirmation threshold.

**Key takeaways:**

- Multisig basics: A multisignature wallet requires multiple private keys for the execution of specific blockchain actions.
- Ownership structure: Ownership of a multisig is decentralized among user addresses known as owners, assigned during deployment and modifiable during regular operation.
- Signers and confirmation process: Signers, owners confirming actions with their private keys, contribute to a confirmation threshold of the multisig.
- Multisig actions: Actions include on-chain operations like transfers, smart contract interactions, and updates to the multisig contract.

## Why use multisigs?

Multisignature wallets are an established tool in the world of web3, offering a robust framework for a collaborative and secure management of shared assets and critical smart contracts.

The main advantage lies in increased security, as multiple private keys are needed for authorization. This significantly reduces the risk of unauthorized access and malicious activities, creating a solid defense against both internal and external threats. By distributing authority among multiple parties, multisigs effectively reduce the potential impact of a compromised key, reinforcing a resilient defense mechanism. Such risk mitigation strategies align seamlessly with the dynamic and often target-rich nature of web3.

In collaborative environments involving shared assets and smart contracts, multisignature wallets introduce a trustless mechanism for decision-making. This ensures that all parties are involved in the authorization process, promoting transparency and reducing reliance on a single entity. Additionally, predefined rules within owner groups play a crucial role in effective dispute resolution. Multisigs require a consensus for any action, preventing unilateral decisions and requiring a broader agreement for fair and transparent governance.

Multisignature wallets are useful in scenarios with multiple parties, enabling secure cross-organizational collaboration. Each participating entity holds a key, and a consensus is essential for any action, finding a balance between cooperation and security.

Furthermore, multisigs can serve as secure personal wallets with a fallback feature. By creating a multisig with multiple personal wallets, the need for multiple confirmations adds an extra layer of security. In the event of theft or loss of access to a single wallet, the multisig assets remain accessible through the unaffected wallets, ensuring continued control over funds.

**Key takeaways:**

- Robust tool: Multisignature wallets in web3 provide a collaborative and secure framework for managing shared assets and critical smart contracts.
- Security advantage: Enhanced security is achieved as multiple private keys are required for authorization, reducing the risk of unauthorized access and mitigating internal and external threats.
- Trustless decision-making: Multisignature wallets enable trustless decision-making, involving all parties in the authorization process for transparency and preventing unilateral decisions.
- Collaborative security: Facilitating secure collaboration among multiple parties, multisigs require consensus for actions, balancing cooperation and security

## How to set up a multisig?

A new multisignature wallet, with the base functionality described above, can be set up practically on any blockchain network that supports smart contracts. However, for most users, reaching out to an established multisig provider is the easiest and most convenient way to go. Using well-known providers ensures high security of the implemented smart contract, better guides and support, and in most cases, a graphical interface for the management of the multisig.

One of the most popular providers is [Safe](https://safe.global), through which more than $420B has been transacted since its launch ([source](https://dune.com/safe/safe-absolute-flows)). It offers a user-friendly interface with easy onboarding and an interactive dashboard. Many other multisig wallet solutions also base their applications on Safe’s smart contracts and tools. Additionally, it supports many different external integrations to enhance its functionality and interactivity.

Of course, alternative solutions are widely available, and the document will point out some of these in later chapters. However, we will not go into detail on how to set up any specific solution. After all, every provider should have a guided onboarding process suitable for the technical level of their target user base.

## How to configure a multisig?

Setting up a multisig may seem trivial at the start of a project, but as operations expand, it is essential to figure out a balanced approach, maximizing both security and responsiveness. With many different aspects contributing to the complexity of this challenge, let’s take a more detailed look at each part:

### Owner count and threshold size

Every multisig smart contract is built on the foundation of a confirmation threshold, requiring a specified number of confirmations (signatures) for an action to be executable. In many cases, this is the first information you will see when reading about details of someone’s multisig. For an X/Y multisig, the X defines the required amount of confirmations (the threshold), and the Y represents the total number of owners of the given multisignature wallet.

There is no general template for establishing these parameters. Every project is different and various aspects play a role in its configuration: value of managed assets and contracts, size of the community, level of decentralization, frequency of actions, and so on.

In the vast majority of cases, you will encounter wallets utilizing a majority threshold. The undisputed security benefits of such an approach are observable in all kinds of environments, way beyond the world of web3. It is much harder to perform any malicious takeovers with such a requirement.

Given a unanimous consensus of a majority, it is reasonable to assume that the rest of the owners would also confirm a pending action. However, opinion disputes can arise and in such scenarios, the majority rule decides the outcome. It is crucial for owners to actively communicate, as a single individual noticing an error in the details of an action should be able to notify others and revert their decision before a fatal execution.

The total size of the owners' group is also a challenging piece of the puzzle. More eyes, more see, and with a larger group, there’s a better chance to spot and identify a mistake. On the other hand, it can contribute to a decreased operational effectiveness of the multisig, requiring confirmation from many individuals for each action.

**Examples of implementation:**

- KlimaDAO, a project aiming to drive climate change via carbon-backed currency, uses a 3/5 multisig for their treasury.
- Aave, a major decentralized cryptocurrency lending platform, has a 6/10 multisig for emergency management of their markets.

**Key takeaways:**

- Owner count and confirmations: Multisig contracts rely on a set number of confirmations from the total pool of owners.
- Configurational variability: No universal multisig configuration template exists; factors like asset value, community size, level of decentralization, and action frequency play a role.
- Security through majority: Majority thresholds enhance security, making malicious takeovers challenging, relying on unanimous consensus for confirmation.
- Communication and decision reversal: Active owner communication is crucial; disputes are resolved via majority rule, and errors can be rectified with proper communication before fatal execution.

### Composition of owners

The composition of individuals assuming ownership of a multisignature wallet is a vital aspect of its functioning. Since various projects have distinct requirements for their multisig setups, there are numerous options available for determining the composition of owners.

For smaller, tightly-knit groups of individuals aiming to enhance the security of their pooled funds, a straightforward and simple configuration is often preferred. Here, the management of the multisig involves active participation from the closest core members, resembling a traditional business setup.

As the fund size expands, especially with contributions from external parties, a more decentralized ownership structure becomes necessary. A parallel can be drawn with traditional businesses, where responsibility is distributed among board members.

The greater a project emphasizes public transparency, the higher the demand for decentralization in its multisig setup. Typically, this responsibility is extended to the project's active contributors, community members, or recognized external parties.

However, communities should also consider the risks of such distributions. For example, an organized group could infiltrate these individual ownership pathways, get assigned to owner roles, and reach the required threshold for control over the multisig. If a project is managing a significant amount of assets in its treasury, such an attack could be worthwhile even if it would be carefully executed over a span of multiple years.

**Examples of implementation:**

- Treasure, a decentralized gaming ecosystem, has a multisig controlled by project founders.
- Nexus Mutual DAO’s multisig ownership, a part of a decentralized insurance protocol, is composed of community members.

**Key takeaways:**

- Security and decentralization: Small groups prefer simple setups; as funds grow, decentralized structures are crucial.
- Transparency impact: Projects emphasizing transparency extend ownership to contributors, community members, or external parties.
- Distribution risks: Despite decentralization, there's a risk of infiltration, with groups exploiting ownership for control over the multisig, particularly with significant assets.

### Owner appointment

Closely related to the composition of the multisig owners is the method of their appointment. This is dependent on the type of project and setup of internal processes.

In smaller, more private projects, founders or core contributors are commonly appointed. There's no requirement for a formal structure; instead, it's a straightforward collaboration among individuals.

As projects become more open to community involvement and prioritize decentralization, they often establish more formalized governance rules. This usually involves implementing a voting process, allowing the community to participate in crucial decisions. Among these decisions, the appointment of multisig owners may also be subject to community voting.

Depending on the project, owner-candidate nominations are typically carried out in two ways:

One approach involves individuals being nominated for the owner role through a proposal; afterward, the community voters have the option to approve or deny such a proposal. This is often seen in more centralized projects, where the core team favors the nomination of well-known contributors and parties.

The other approach involves self-nomination or nomination of community members. Provided that they meet the role requirements, the process moves to an election stage where the top nominees are voted into their roles through a proposal voting system.

**Examples of implementation:**

- Nest Wallet’s founding members are also the multisig owners.
- BanklessDAO, a project onboarding people to crypto, votes in multisig owners through community elections.

**Key takeaways:**

- Private projects: Founders or core contributors are commonly appointed without formal governance.
- Community involvement: Open projects prioritize decentralization with formal governance, allowing community participation in decisions, including multisig owner appointments.
- Nomination methods: Proposals involve community voting on nominated individuals; the election stage includes self-nomination or community nominations, leading to a vote on top candidates through a proposal system.

### Owner terms

In appointing owners, it is important to define policies related to this role, a crucial component being the length of the owner role term. Owner terms can be specified as a fixed duration, typically ranging from 3 to 12 months, or left indefinite. Regardless, such duration should be explicitly stated. On the other hand, similar to traditional governance practices, a maximum number of consecutive owner terms for an individual may also be established.

Role terms ensure the responsiveness of the multisig. Many projects face challenges when owners become gradually inactive, leading to a decline in the overall performance of the multisig. In the worst cases, it can even result in a majority of owners neglecting their duties and seriously hampering all operations of the project.

Nonetheless, time constraints should be only a safety mechanism of the last resort. It is in each project’s own interest to demand reasonable activity from their multisig owners and to continuously monitor it.

**Examples of implementation:**

- Owners of Hop DAO’s multisig, a token bridge protocol, are voted in every 6 months.
- Balancer, a decentralized finance platform, requires its multisig owners to be active at least once every 3 months or the last 2 votes (whichever takes longer).

**Key takeaways:**

- Owner term policies: Crucial to define policies for owner roles, including term length (fixed or indefinite) and limits on consecutive terms.
- Role term importance: Specified terms ensure multisig responsiveness, preventing issues from owner inactivity that can hamper project operations.
- Balancing safety and activity: Projects should demand reasonable activity from owners, treating term limits as a last resort and continuously monitoring owner engagement.

### Owner identities

Another important aspect to consider when setting up a multisignature wallet is whether the actual identities of owners should be disclosed. Like any other decision, this comes with its own set of advantages and disadvantages.

For multisig owner roles, candidates can be asked to disclose their identities by verifying through reputable third parties. From one standpoint, this process, sometimes referred to as “doxing” (though meaning of this word has different meanings based on the context), enhances their trustworthiness, transparency, and possibly even their liability.

On the other hand, known identities can take attackers one step closer to their malicious objectives. Thus, it is extremely important for individuals with public identities to prioritize security, both online and in real-life activities.

The choice of whether to disclose owners depends on the nature of the project. It wouldn't be practical, for instance, to publicly identify owners for a small, discreet project led by a small group of people.

**Key takeaways:**

- Verification for trust: Owners can verify through third parties for trust and transparency.
- Security caution: Known identities may expose owners, requiring public figures to prioritize security.

### Signer reward systems

For founders of smaller projects, who are heavily committed to the project's efficiency and operability, and also hold multisig owner roles, the reward for their work is nonessential. As projects grow and multisig participants get gradually more distant from the project’s founding core, incentives become a reasonable tool for rewarding their roles and responsibilities. A good reward system should compensate signers for their responsiveness and time committed to reviewing individual actions. It should also align reasonably with the value of managed assets and the frequency of multisig actions. As expected, this also introduces its own set of challenges as numerous variables come into play, and risks abound from various angles.

#### Reward frequency

Many projects that employ signer incentives distribute equal rewards to all multisig owners at regular intervals, such as monthly or at the end of their owner role term. Although this approach may seem intuitive, it creates a situation where owners can become inactive yet still receive rewards. This can result in an unfair compensation structure for active signers. In more severe cases, the majority of owners may become inactive, negatively impacting the operations of the multisig and compromising the efficiency of the whole setup.

A logical countermeasure would be to reward only the actively participating signers. However, this approach also introduces serious risks by fostering a competitive environment where speed becomes more important than a thorough review of multisig actions. This setup might lead signers to overlook details in pending actions to secure personal rewards, ultimately compromising the heightened security promised by the multisignature feature.

Each project must determine its own optimal balance between responsiveness and security for its multisignature wallet. The key to finding and maintaining this balance is continuous monitoring and evaluation of multisig effectiveness. Ideally, owners should be familiarized with activity and responsiveness requirements before the start of their term, and other project members should keep them consistently accountable for it.

**Examples of implementation:**

- Mutant Cats DAO, an NFT-related project, rewards its multisig owners every month.
- Sushi, a decentralized exchange platform, provides rewards to its multisig owners annually.

**Key takeaways:**

- Reward frequency risks: Equal rewards to all owners may lead to inactivity and unfairness, and exclusively rewarding active signers poses security risks by prioritizing speed over thorough reviews.
- Optimal balance: Projects need to find a balance between responsiveness and security through continuous monitoring and evaluation.
- Preventive measures: Owners should be familiar with activity requirements, maintaining accountability for a balanced multisig operation.

#### Reward currency

When defining the form of rewards, many projects choose to further increase individuals’ investment in it by providing rewards in the project’s token - if available. Considering the volatility of the market and the length of owner role terms, it is often preferable to define rewards in traditional currencies or stablecoins. At the period of payout, the reward amount is converted into the token for the market value and transferred to the receiver. If a project is not associated with any token, rewards in stablecoins are a sufficient option.

**Examples of implementation:**

- mStable, a decentralized finance infrastructure, provides USD rewards in its MTA token equivalent at the payout date.
- Gearbox Protocol, a decentralized finance protocol, rewards its multisig owners in a predefined amount of their GEAR token.

**Key takeaways:**

- Reward stability: Projects opt for rewarding in their token to boost individual investment, but due to market volatility and owner term lengths, defining rewards in traditional currencies or stablecoins may be preferable.

#### Reward amount

Arguably, the most intricate component of the reward system is the determination of the actual reward amount. This decision hinges on the financial resources available to each project and the importance it places on its security. Additional expenditures can originate from the extent of the duties and responsibilities connected to the role of multisig owner. While there is no universally recommended amount for these reasons, we’ll further explain the most common process of multisig owners to better illustrate their time and focus demands.

Each multisig action begins with the submission of its details, and the format varies depending on the governance interfaces and tools employed. This process may involve manual data entry, uploading CSV files, or confirming submitted asset transfer requests. Accuracy in input data is crucial at this stage as it sets the foundation for the subsequent procedures. An action may involve only a single command or extend to multiple commands, demanding time and attention from the submitter, especially due to the intricacies of alphanumeric data involved. This task is usually carried out by an individual but cooperation with other owners is possible.

A submitted action must be signed by multisig owners to reach the required confirmation threshold. During this step, signers verify that the data accurately reflects the proposed actions from the original data source. For each specific action, they must confirm the accuracy of all parameters (such as target address, token, token amount, etc.). This process can be demanding in terms of attention and time, varying based on the action details and the number of sub-actions involved.

The last step of the process involves the on-chain execution, which is the most straightforward part. A possible time-consuming task is monitoring low gas fees on some of the expensive blockchains. Based on the internal agreement of the owners, this step can be left for the last signer or a dedicated owner can be assigned to it.
When defining the reward system, one should consider the overall expected activity during the owner's term with all the demands associated with each action.

**Examples of implementation:**

- Ribbon Finance, a decentralized finance platform, rewards its multisig members with an equivalent of 150-350 USD per month.
- dYdX Foundation, a maintainer of a decentralized finance platform, compensates its core contributors with 1100 USD per month in a role that includes other duties besides multisig management.

**Key takeaways:**

- Reward amount determination: Depends on project resources, security importance, and duties.
- Role considerations: When defining owner rewards, project leaders should consider the demands of action submission, confirmation, and execution, taking into account the overall expected activity during the owner's term.

### Additional security measures

Thanks to the modularity of smart contracts, projects with specific needs and objectives can optionally implement some additional features into their multisig setups:

#### Timelock

Timelock is an additional feature that integrates a time delay between action confirmation and execution. This feature is commonly found in projects with deeply engaged communities, particularly in areas like decentralized finance (DeFi) or staking platforms, where assets are programmatically managed through code.

In situations where proposed changes to the project's operations do not align with an individual's sentiment, they can use the timelock period to take necessary preventive actions, such as withdrawing their funds.

**Examples of implementation:**

- Gitcoin DAO, a public goods community funding platform, uses the timelock feature in its governance system.

**Key takeaways:**

- Timelock functionality: Timelock introduces a delay between action confirmation and execution, enabling users to take preventive actions if changes don't align with their sentiments.

#### Veto power

The veto empowers specific individuals in a project to annul confirmed actions before their execution. This function can be implemented either during the confirmation period or the timelock period, with the primary functionality remaining consistent. This is especially useful for projects where actions can be proposed and voted for by the community (see alternative setups chapter). It can prevent various types of errors and malicious attacks, from input and validation errors to hostile governance takeovers.

**Examples of implementation:**

- Arbitrum DAO, a part of the Arbitrum network, implements veto power for emergency operations of its multisig.

**Key takeaways:**

- Veto mechanism: Empowers specific individuals to cancel confirmed actions before execution, crucial for preventing errors and attacks in community-voted projects.

### Alternative setups

Multisignature wallets with setups described above are not the only available option for decentralized governance. A popular alternative is the Governor contract, offering voting power through token delegation. Users have the option to delegate to a third party or engage directly by self-delegating if they wish to participate.

Projects can specify proposal submission threshold and users with exceeding voting power can submit proposals for actions. Many projects set this value to 1% of the total token cap, but each project can select its preferred value. Similarly, a threshold for voting for the action is predefined, which when met during the voting period will then pass the action into a timelock queue. While in the timelock, optional veto functionality is available. Also, if the voting power drops below the submission threshold, the action will be canceled.

There are multiple versions of the Governor contract. The original version by Compound, Governor Alpha, was set up as an immutable contract, meaning every change to parameters (e.g. threshold, voting period, etc.) required the deployment of a new contract and transfer of ownership. Later versions, such as Governor Bravo, allowed for upgrades and changes to the governance parameters without migrating.

**Examples of implementation:**

- Uniswap Foundation, a decentralized finance protocol, utilizes the Governor contract for its community governance processes.

**Key takeaways:**

- Governance options: Governor contract allows decentralized governance through token delegation, either via third-party delegation or direct self-delegation.
- Proposal and voting: Users with enough voting power can submit proposals, meeting project-defined thresholds, and actions go to a timelock with optional veto; if voting power drops, the action is canceled.

## How to operate a multisig?

Being a multisignature wallet owner entails a significant amount of responsibility and time commitments. Even an inaccuracy in a single character of action data can result in fatal consequences, costing the project substantial financial assets or losing control over crucial contracts.

In this section, we will take a look at the duties and responsibilities of multisig owners to educate and minimize the risk of errors during common multisig operations.

### Action submission

Depending on the arrangement within a group of multisig owners, the duty of submitting an action into a multisig may be assigned to either one person or multiple people, though only a single individual can submit an action at any given time. Regardless of the arrangement, this person should be familiar with the interface of the multisig wallet they are using.

As we have briefly established in a previous chapter, the process of action submission can differ from project to project, but the objective is the same – create a new action based on some predefined action request. The request can have various forms based on the internal procedures and interfaces that individual projects use. For example, it could involve inputting a CSV file from the project's accounting team into the Safe Wallet interface or confirming payment requests on Request Finance. You’ll be able to learn about some of these tools in the later chapters.

In this step, accuracy is the primary objective. The owner submitting the action should validate that the action data is the same as the data in the action request. Based on the type of the action, this can include, but is not limited to, the target address, token type, and token amount.

Given that action submission often includes an automatic confirmation by the submitter, it is crucial that they also fulfill their responsibilities for confirming the action during this step. This is even more important for multisigs with low confirmation thresholds.

**Key takeaways:**

- Submission responsibility: Multisig owners, whether one person or a group, assign the duty of action submission to a familiar individual, involving creating actions based on predefined requests with accuracy in validating data.
- Accuracy demands: During action submission, accuracy is crucial, and the submitter, often with automatic confirmation, must fulfill their responsibility, especially in multisigs with low confirmation thresholds.

### Action confirmation

The confirmation and signing of an action is an essential responsibility of a multisig wallet owner. Each action demands focus and time, as any error in the data must be identified during this step.

To effectively review the action data, the owners should be able to access the original action request used by the action submitter for comparison. Similar to the previous step, owners should validate the accuracy of the data between the action request and the submitted action.

Owners must have a clear understanding of the rationale behind each action. Any inaccuracies or unknown data should prompt questions and discussions within a larger group. It is crucial to verify that every address, function call, token, and amount is relevant to the intended action and correctly reflected in the submitted action.

This step is the firewall step, where both unintentional errors and malicious attacks should come to light. It falls on the multisig owners to identify these threats. The review process might be lengthy, tedious, and somewhat repetitive, but the potential risks of loss of finances or control should always outweigh its needs.

It is worth noting that numerous multisig wallet interfaces and providers now offer features to assist owners in validating pending actions. For example, the modularity of Safe's contracts enables the implementation of plugins, allowing for the whitelisting of target addresses. Consequently, actions can only be submitted if all target addresses have been previously whitelisted.

Additionally, Safe offers a cost-free alternative for labeling addresses using their address book feature, enabling users to assign names to individual addresses. Any unlabelled addresses should therefore automatically raise awareness of a potential issue.

Towards the end of 2023, attacks were executed by creating deceptive addresses that closely resembled those previously used by victims. Attackers initiated zero-value transfers to victims' wallets, and during subsequent actions, victims unintentionally copied the attacker's address from the transaction history, resulting in fund transfers to the attackers. The implementation of address whitelisting and labeling could have effectively prevented many of these incidents.

Ideally, signers should respond to actions within a reasonable timeframe as defined before the role appointment. However, threats can also occur internally when there are requests for swift action confirmation. It is important to always remember that speed should never take precedence over careful consideration of all action details.

In another recent incident, Gitcoin experienced an event involving the misallocation of treasury funds, resulting in a loss of approximately half a million dollars. The transfer of the MMM’s S19 budget was intended for the multisig wallet but was mistakenly sent to the token address. Unfortunately, as with most cases like this, the fund was irrecoverable.

**Key takeaways:**

- Critical step: Confirming multisig actions is vital, demanding focus and time to identify errors in the data.
- Verification and security: Owners must access the original action request for effective review, validating data accuracy and ensuring a clear understanding of each action's rationale.
- Security measures: This step acts as a firewall against errors and attacks; response time to actions should align with predefined timeframes, but always prioritizing careful consideration over speed.

### Action execution

Once an action is confirmed by signers, fulfilling the required threshold, it is available for on-chain execution. Similar to the first step, action submission, this step can be performed only by a single person. It is essentially the same as any on-chain execution in a regular crypto wallet, submitting and executing an action on the blockchain.

This on-chain action, as any other, requires the actor to pay network gas fees. It is up to the decision of the project’s members to assign a single person to this step or allow anyone to do it. It is not uncommon for projects with smaller funds to delay executions until lower network fees are available. Nonetheless, most projects reimburse the actors for the gas they’ve paid.

**Key takeaways:**

- On-chain execution: After confirmation by signers, on-chain execution of a multisig action can be performed by a single person, similar to regular crypto wallet transactions.
- Gas fees and responsibility: The individual executing the on-chain action incurs network gas fees, a decision typically made by the project's members, with reimbursement common in most projects.

## Tools, tips, and tricks

### Address labeling in Safe

The Safe’s wallet interface offers a built-in address labeling feature, available under the Address Book tab. By providing a custom name for each given address, you’ll be able to easily identify familiar participants in the details of any transactions. This is a valuable security measure, as malicious exploits through similarly looking addresses are not uncommon. With custom address labels, you’ll be able to confidently confirm the accuracy of any action data, as any unlabeled addresses should raise your awareness. However, keep in mind that labels are not synchronized across multiple browsers and devices.

Learn how to use the address book through [Safe’s official guide](https://help.safe.global/en/articles/40861-how-to-use-the-address-book).

### Extending Safe with Modules

Safe Modules are an optional feature for extending Safe’s core smart contracts with additional functionality. Modules can include daily spending allowances, amounts that can be spent without the approval of other owners, recurring transaction modules, and standing orders performed on a recurring date. As smart contracts, adding or removing modules requires confirmation from the configured threshold of multisig owners. For the same reason, modules can execute arbitrary actions and take over a whole multisig; use only trusted and audited modules.

Read more about Safe Modules and gain technical insights in [Safe’s documentation](https://docs.safe.global/safe-smart-account/modules).

### Building on Safe’s wallet with Apps

Embracing the collaborative and open nature of web3, Safe maintains an extensive list of projects and applications building on Safe’s foundations. The types of available integrations are truly diverse, covering areas such as accounting, DAO tooling, decentralized finance, fundraising, governance, marketplaces, and more. Chances are, if you’re looking for a specific feature, some Safe App already offers it.

Explore the Safe Apps in the [ecosystem directory](https://safe.global/ecosystem).

### Den’s understandable transaction details

Den is a powerful multisig interface and toolkit built on Safe’s foundation, enabling teams to create, review, and execute transactions more effectively. Some of its primary advantages are easy-to-read labels, input fields, and notifications on various communication platforms. By using Den, you and your teammates will be able to promptly react to new transactions and easily understand all its inputs and outcomes before signing.

See how Den can help you to get transactions signed and executed fast at [onchainden.com](https://www.onchainden.com).

### Managing crypto spending with Request Finance

To support the handling of crypto expenses, Request Finance has created a comprehensive crypto treasury management system that allows individuals and businesses to manage all their crypto invoicing, payroll, and expenses in one place. If projects incur corporate expenses in fiat or crypto, the app offers reviews, approvals, and mass payouts for expense reimbursement.

Improve and manage your spending with a fast and compliant experience at [request.finance](https://www.request.finance).

### Community-led governance on Tally

Focusing on truly decentralized projects with community-led governance, Tally provides an extensive platform handling all related complexities so that members can focus on more important tasks. The platform offers a home page for each project as a single source of information necessary for the project’s governance, seamlessly integrating features for the management of proposals, proposal voting, and voting power delegation.

Govern your project with the direct involvement of the community with [Tally](https://www.tally.xyz).

### Multisig analytics by Multisight

Multisight is an analytics tool for evaluating the response activity of multisigs. It allows effective optimization of multisig processes by providing new analytical views on signers and transactions, enabling the identification of bottlenecks, promoting accountability, and speeding up team operations.

Gain insight into the operations of your multisig with [Multisight](https://multisight.app).

### Protect your crypto with Wallet Guard

Though being primarily associated only with crypto wallets for individuals, the Wallet Guard helps users prevent phishing attempts and other types of malicious attacks. As a browser extension, it provides a protective layer by proactively scanning users’ web addresses and notifying them about websites that have been associated with scams or have low trust in general. For personal wallets, it also displays easy-to-read details of every transaction.

Keep your assets protected with [Wallet Guard](https://www.walletguard.app).
