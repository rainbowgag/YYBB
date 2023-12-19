ruleset=🚀 节点选择,[]DOMAIN-SUFFIX,xn--ngstr-lra8j.com
ruleset=🚀 节点选择,[]DOMAIN-SUFFIX,services.googleapis.cn
ruleset=🚀 节点选择,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/Ruleset/GoogleCNProxyIP.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/LocalAreaNetwork.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/UnBan.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/ChinaDomain.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/ChinaMedia.list
ruleset=REJECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/BanAD.list
ruleset=REJECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/BanProgramAD.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/ChinaCompanyIp.list
ruleset=DIRECT,https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/ChinaIp.list
ruleset=DIRECT,[]GEOIP,CN,no-resolve
ruleset=🚀 节点选择,[]FINAL

proxy-groups:
  - name: "🚀 节点选择"
    type: select
    proxies:
      - "🇭🇰 香港节点"
      - "♻️ 自动选择"
      - DIRECT
  - name: "♻️ 自动选择"
    type: url-test
    proxies: 
      - "*" # 确保这里列出了所有代理节点名称或者使用 '*' 来选择所有节点
    url: "http://www.gstatic.com/generate_204"
    interval: 300
    tolerance: 50
  - name: "🇭🇰 香港节点"
    type: url-test
    proxies: 
      - "*HK*" # 确保这里的正则表达式正确匹配您的香港节点名称
    url: "http://www.gstatic.com/generate_204"
    interval: 300
    tolerance: 50

rule-providers:
  # ... (这里包含了您的规则提供者定义)

rules:
  # ... (这里包含了您的规则定义)

enable_rule_generator: true
overwrite_original_rules: true
