# terraform-aws-waf-owasp-top-10-rules

[![Terraform Version](https://img.shields.io/badge/Terraform%20Version->=0.13.0,_<0.14.0-blue.svg)](https://releases.hashicorp.com/terraform/)
[![Release](https://img.shields.io/github/v/release/traveloka/terraform-aws-waf-owasp-top-10-rules.svg)](https://github.com/traveloka/terraform-aws-waf-owasp-top-10-rules/releases)
[![Last Commit](https://img.shields.io/github/last-commit/traveloka/terraform-aws-waf-owasp-top-10-rules.svg)](https://github.com/traveloka/terraform-aws-waf-owasp-top-10-rules/commits/master)
[![Issues](https://img.shields.io/github/issues/traveloka/terraform-aws-waf-owasp-top-10-rules.svg)](https://github.com/traveloka/terraform-aws-waf-owasp-top-10-rules/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/traveloka/terraform-aws-waf-owasp-top-10-rules.svg)](https://github.com/traveloka/terraform-aws-waf-owasp-top-10-rules/pulls)
[![License](https://img.shields.io/github/license/traveloka/terraform-aws-waf-owasp-top-10-rules.svg)](https://github.com/traveloka/terraform-aws-waf-owasp-top-10-rules/blob/master/LICENSE)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)

## Description

OWASP Top 10 Most Critical Web Application Security Risks is a powerful awareness document for web application security. It represents a broad consensus about the most critical security risks to web applications. Project members include a variety of security experts from around the world who have shared their expertise to produce this list[[1]](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project). You can read the document that they published here: [[2]](https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf).

This is a Terraform module which creates AWF WAF resources for protection of your resources from the OWASP Top 10 Security Risks. This module is based on the whitepaper that AWS provides. The whitepaper tells how to use AWS WAF to mitigate those attacks[[3]](https://d0.awsstatic.com/whitepapers/Security/aws-waf-owasp.pdf)[[4]](https://aws.amazon.com/about-aws/whats-new/2017/07/use-aws-waf-to-mitigate-owasps-top-10-web-application-vulnerabilities/).

This module will only create match-sets[[5]](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-create-condition.html), rules[[6]](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-rules.html), and a rule group (optional)[[7]](https://docs.aws.amazon.com/waf/latest/developerguide/working-with-rule-groups.html).
Those resources cannot be used without WebACL[[8]](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-working-with.html), which is not covered by this module.

To see the example on how to provision the resources only, check [Examples](#examples) section.

But to see the example on how to use this module together with WebACL to fully protect your application, see this page: [[9]](https://github.com/traveloka/terraform-aws-waf-webacl-supporting-resources/tree/master/examples)

References
* [1] : https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project
* [2] : https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf
* [3] : https://d0.awsstatic.com/whitepapers/Security/aws-waf-owasp.pdf
* [4] : https://aws.amazon.com/about-aws/whats-new/2017/07/use-aws-waf-to-mitigate-owasps-top-10-web-application-vulnerabilities/
* [5] : https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-create-condition.html
* [6] : https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-rules.html
* [7] : https://docs.aws.amazon.com/waf/latest/developerguide/working-with-rule-groups.html
* [8] : https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-working-with.html
* [9] : https://github.com/traveloka/terraform-aws-waf-webacl-supporting-resources/tree/master/examples

## Prerequisites
### FAQ
1. **Can I use only some of the rules?** *Yes you can. This module will outputs the rules' ID. Attach to WebACL you created only the IDs of the rules that you want.*
2. **Can I provision only some of the rules?** *No you can't. If you really want to do it, the only solution is to copy-paste match-sets and rules code manually. You must aware that by doing that you will lose support from maintainer of this module.*
3. **Can I modify some match-sets of a rule?** *No you can't. The same answer to answer question number 2. But if you found something need to be fixed, e.g. match-sets causing lots of false positive, please don't hesitate to create an issue or a pull request to this repository!*

### Examples
* [owasp-top-10](examples/owasp-top-10)

### Related Modules
* [terraform-aws-waf-webacl-supporting-resources](https://github.com/traveloka/terraform-aws-waf-webacl-supporting-resources)

## Dependencies

This Terraform module has no dependencies to other modules

## Terraform Versions

Created and tested using Terraform version `0.11.14`


<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_random"></a> [random](#provider\_random) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_waf_byte_match_set.owasp_02_auth_token_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_byte_match_set.owasp_04_paths_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_byte_match_set.owasp_06_php_insecure_qs_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_byte_match_set.owasp_06_php_insecure_uri_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_byte_match_set.owasp_08_csrf_method_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_byte_match_set.owasp_09_server_side_include_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_byte_match_set) | resource |
| [aws_waf_rule.owasp_01_sql_injection_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_02_auth_token_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_03_xss_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_04_paths_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_06_php_insecure_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_07_size_restriction_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_08_csrf_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule.owasp_09_server_side_include_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule) | resource |
| [aws_waf_rule_group.owasp_top_10](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_rule_group) | resource |
| [aws_waf_size_constraint_set.owasp_07_size_restriction_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_size_constraint_set) | resource |
| [aws_waf_size_constraint_set.owasp_08_csrf_token_size_constrain_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_size_constraint_set) | resource |
| [aws_waf_sql_injection_match_set.owasp_01_sql_injection_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_sql_injection_match_set) | resource |
| [aws_waf_xss_match_set.owasp_03_xss_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/waf_xss_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_02_auth_token_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_04_paths_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_06_php_insecure_qs_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_06_php_insecure_uri_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_08_csrf_method_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_byte_match_set.owasp_09_server_side_include_string_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_byte_match_set) | resource |
| [aws_wafregional_rule.owasp_01_sql_injection_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_02_auth_token_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_03_xss_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_04_paths_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_06_php_insecure_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_07_size_restriction_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_08_csrf_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule.owasp_09_server_side_include_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule) | resource |
| [aws_wafregional_rule_group.owasp_top_10](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_rule_group) | resource |
| [aws_wafregional_size_constraint_set.owasp_07_size_restriction_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_size_constraint_set) | resource |
| [aws_wafregional_size_constraint_set.owasp_08_csrf_token_size_constrain_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_size_constraint_set) | resource |
| [aws_wafregional_sql_injection_match_set.owasp_01_sql_injection_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_sql_injection_match_set) | resource |
| [aws_wafregional_xss_match_set.owasp_03_xss_set](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafregional_xss_match_set) | resource |
| [random_id.this](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/id) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_create_rule_group"></a> [create\_rule\_group](#input\_create\_rule\_group) | All rules can be grouped into a Rule Group. Unfortunately, AWS WAF Rule Group limit per region is only 3. By setting the value to `false` will not create the rule group. Default to `true`. | `string` | `"true"` | no |
| <a name="input_csrf_expected_header"></a> [csrf\_expected\_header](#input\_csrf\_expected\_header) | The custom HTTP request header, where the CSRF token value is expected to be encountered | `string` | `"x-csrf-token"` | no |
| <a name="input_csrf_expected_size"></a> [csrf\_expected\_size](#input\_csrf\_expected\_size) | The size in bytes of the CSRF token value. For example if it's a canonically formatted UUIDv4 value the expected size would be 36 bytes/ASCII characters. | `string` | `"36"` | no |
| <a name="input_description"></a> [description](#input\_description) | The description of these resources. | `string` | n/a | yes |
| <a name="input_environment"></a> [environment](#input\_environment) | The environment of these resources belong to. | `string` | n/a | yes |
| <a name="input_max_expected_body_size"></a> [max\_expected\_body\_size](#input\_max\_expected\_body\_size) | Maximum number of bytes allowed in the body of the request. If you do not plan to allow large uploads, set it to the largest payload value that makes sense for your web application. Accepting unnecessarily large values can cause performance issues, if large payloads are used as an attack vector against your web application. | `string` | `"4096"` | no |
| <a name="input_max_expected_cookie_size"></a> [max\_expected\_cookie\_size](#input\_max\_expected\_cookie\_size) | Maximum number of bytes allowed in the cookie header. The maximum size should be less than 4096, the size is determined by the amount of information your web application stores in cookies. If you only pass a session token via cookies, set the size to no larger than the serialized size of the session token and cookie metadata. | `string` | `"4093"` | no |
| <a name="input_max_expected_query_string_size"></a> [max\_expected\_query\_string\_size](#input\_max\_expected\_query\_string\_size) | Maximum number of bytes allowed in the query string component of the HTTP request. Normally the  of query string parameters following the ? in a URL is much larger than the URI , but still bounded by the  of the parameters your web application uses and their values. | `string` | `"1024"` | no |
| <a name="input_max_expected_uri_size"></a> [max\_expected\_uri\_size](#input\_max\_expected\_uri\_size) | Maximum number of bytes allowed in the URI component of the HTTP request. Generally the maximum possible value is determined by the server operating system (maps to file system paths), the web server software, or other middleware components. Choose a value that accomodates the largest URI segment you use in practice in your web application. | `string` | `"512"` | no |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | The name of the product domain these resources belong to. | `string` | n/a | yes |
| <a name="input_service_name"></a> [service\_name](#input\_service\_name) | The name of the service these resources belong to. | `string` | n/a | yes |
| <a name="input_target_scope"></a> [target\_scope](#input\_target\_scope) | Valid values are `global` and `regional`. If `global`, means resources created will be for global targets such as Amazon CloudFront distribution. For regional targets like ALBs and API Gateway stages, set to `regional` | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_rule01_sql_injection_rule_id"></a> [rule01\_sql\_injection\_rule\_id](#output\_rule01\_sql\_injection\_rule\_id) | AWS WAF Rule which mitigates SQL Injection Attacks. |
| <a name="output_rule02_auth_token_rule_id"></a> [rule02\_auth\_token\_rule\_id](#output\_rule02\_auth\_token\_rule\_id) | AWS WAF Rule which blacklists bad/hijacked JWT tokens or session IDs. |
| <a name="output_rule03_xss_rule_id"></a> [rule03\_xss\_rule\_id](#output\_rule03\_xss\_rule\_id) | AWS WAF Rule which mitigates Cross Site Scripting Attacks. |
| <a name="output_rule04_paths_rule_id"></a> [rule04\_paths\_rule\_id](#output\_rule04\_paths\_rule\_id) | AWS WAF Rule which mitigates Path Traversal, LFI, RFI. |
| <a name="output_rule06_php_insecure_rule_id"></a> [rule06\_php\_insecure\_rule\_id](#output\_rule06\_php\_insecure\_rule\_id) | AWS WAF Rule which mitigates PHP Specific Security Misconfigurations. |
| <a name="output_rule07_size_restriction_rule_id"></a> [rule07\_size\_restriction\_rule\_id](#output\_rule07\_size\_restriction\_rule\_id) | AWS WAF Rule which mitigates abnormal requests via size restrictions. |
| <a name="output_rule08_csrf_rule_id"></a> [rule08\_csrf\_rule\_id](#output\_rule08\_csrf\_rule\_id) | AWS WAF Rule which enforces the presence of CSRF token in request header. |
| <a name="output_rule09_server_side_include_rule_id"></a> [rule09\_server\_side\_include\_rule\_id](#output\_rule09\_server\_side\_include\_rule\_id) | AWS WAF Rule which blocks request patterns for webroot objects that shouldn't be directly accessible. |
| <a name="output_rule_group_id"></a> [rule\_group\_id](#output\_rule\_group\_id) | AWS WAF Rule Group which contains all rules for OWASP Top 10 protection. |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/LICENSE) file for details.https://github.com/siahaanbernard)
