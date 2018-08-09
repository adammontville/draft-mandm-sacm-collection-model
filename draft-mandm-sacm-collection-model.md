---
title: Endpoint Attribute Collection Model
abbrev: Collection Model
docname: draft-mandm-sacm-collection-model-latest
stand_alone: true
ipr: trust200902
area: Security
wg: SACM Working Group
kw: Internet-Draft
cat: std
coding: us-ascii
pi:
  toc: yes
  sortrefs: yes
  symrefs: yes

author:
- ins: A. Montville
  name: Adam W. Montville
  org: Center for Internet Security
  abbrev: CIS
  email: adam.w.montville@gmail.com
  street: 31 Tech Valley Drive
  code: '12061'
  city: East Greenbush
  region: NY
  country: USA
- ins: B. Munyan
  name: Bill Munyan
  org: Center for Internet Security
  abbrev: CIS
  email: bill.munyan.ietf@gmail.com
  street: 31 Tech Valley Drive
  code: '12061'
  city: East Greenbush
  region: NY
  country: USA

normative:
  mandm-sacm-endpont-attribute-data-model-registry:
  mandm-sacm-architecture-redux:


informative:



--- abstract

This memo describes an information model (and associated data model) that can be used to encapsulate detailed endpoint attribute expressions for the purpose of performing collection of actual endpoint attributes in support of assessment.

WORKING GROUP: The source for this draft is maintained in GitHub.  Suggested changes should be submitted as pull requests at https://github.com/adammontville/draft-mandm-sacm-collection-model.  Instructions are on that page as well.

--- middle


# Introduction

Collecting state information from endpoints of any classification is a challenging task without understanding the details of those endpoints. In fact, this challenge represents one of the barriers to speeding policy to implementation in the enterprise - policy authors might know at an abstract level which endpoint attribute they'd like to collect, but they may not understand with enough detail how to express this in a machine readable form.

This may be the result of so many different collection mechanisms. SSH, WinRM, PowerShell Remoting, SOAP-based services, NETCONF/RESTCONF, YANG Push, OVAL, basic command output capture, shell scripts, and the list probably goes on - the list may be as long as there are services on endpoints to query. If we really want to get from policy to implementation quickly, the expression of collection must be reasonably decoupled from the machine readable expression of that collection.

In this regard, we have expressed the notion of collection in its minimal form. The balance of this document describes this minimal form in detail. We begin with an information model and present initial XML and JSON bindings.

[NOTE: We are not averse to other bindings being offered.]

# Terms and Definitions

TBD

# Collection Expression Information Model

[Overview of the entire IM]

## Objects

[Descriptions of what an "object" is. Seems to be a superset of endpoint attributes; or that "thing" from which we can extract attributes.]

## Filters

[Description of why we need filters and what they are. Include any implications, i.e. this may imply some degree of "evaluation" (for the purpose of filtering) wherever the collection process is executing.]

## Variables

[Describe the variable hierarchy and what each means. Dive into local variables and the different constructions present in that element.]

## Formal Information Model

[Pull all of the above together into a concise information model in this subsection.]

# Collection Expression JSON Binding

[Put forward a JSON binding for Collection Expression.]

# Collection Expression XML Binding

[Convert the collection XML from the 102 hackathon (below) to a schema that binds to the previously described information model.]

    <collection>
      <objects>
        <object></object>
      </objects>
      <filters>
        <filter></filter>
      </filters>
      <variables>
        <constant-variable></constant-variable>
        <external-variable></external-variable>
        <local-variable>
          [function-groups, literal-component, variable-component, object-component]
          <arithmetic></arithmetic>
          <begin></begin>
          <concat></concat>
          <end></end>
          <escape-regex></escape-regex>
          <split></split>
          <substring></substring>
          <time-difference></time-difference>
          <regex-capture></regex-capture>
          <unique></unique>
          <count></count>
          <glob-to-regex></glob-to-regex>
        </local-variable>
      </variables>
    </collection>


#  IANA Considerations

[Whether there are IANA considerations remains TBD. It may ultimately be that the decoupling of collection details from abstract collection instruction requires a registry for new collection details...]

#  Security Considerations

TBD

#  Acknowledgements

TBD

#  Change Log

TBD


# Contributors

TBD

--- back

# Examples

[Consider adding one or more examples here.]

# The Attic

TBD
