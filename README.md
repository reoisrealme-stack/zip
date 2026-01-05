# YAML에 이미 rule.name이 있으면 그것을 사용, 없으면 CSV의 시나리오 명 사용
if "rule" not in rule_data:
    rule_data["rule"] = {}

# YAML에 rule.name이 이미 있는지 확인
yaml_rule_name = rule_data.get("rule", {}).get("name", "")

if not yaml_rule_name:
    # YAML에 rule.name이 없을 때만 CSV의 시나리오 명 사용
    rule_data["rule"]["name"] = rule_name
else:
    # YAML의 rule.name이 있으면 그대로 유지
    rule_name = yaml_rule_name  # file_base 생성을 위해 변수도 업데이트
