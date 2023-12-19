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

custom_proxy_group=🚀 节点选择`select`[]🇭🇰 香港节点`[]♻️ 自动选择`[]DIRECT`.*
custom_proxy_group=♻️ 自动选择`url-test`.*`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇭🇰 香港节点`url-test`.*HK.*`http://www.gstatic.com/generate_204`300,,50

enable_rule_generator=true
overwrite_original_rules=true

proxy-groups:
  - name: "🚀 节点选择"
    type: select
    proxies:
      - "♻️ 自动选择"
      - "🇭🇰 香港节点"
      - "DIRECT"
      # ... 其他代理组或节点

  - name: "♻️ 自动选择"
    type: url-test
    proxies: 
      - "香港节点1"
      - "香港节点2"
      # ... 其他非香港的代理节点
    url: "http://www.gstatic.com/generate_204"
    interval: 300
    tolerance: 50

  - name: "🇭🇰 香港节点"
    type: url-test
    proxies: 
      - "{自动填充香港节点列表}"
    url: "http://www.gstatic.com/generate_204"
    interval: 300
    tolerance: 50
