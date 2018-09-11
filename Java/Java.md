---
title: Java
date: 2018-08-22 17:38:42
tags:
categories:
---



<!--more-->

### Java String to int

```java
// 1
	String number = "10";
	int result = Integer.parseInt(number);			
	System.out.println(result);
// 2
	String number = "10";
	Integer result = Integer.valueOf(number);		
	System.out.println(result);
// In summary, parseInt(String) returns a primitive int, whereas valueOf(String) returns a new Integer() object.
```

### getData

<https://tool.lu/timestamp/>

### 数据库-Java后台-前端 传值

##### JSON

`sql`

```xml
<select id="selectcitytop" resultType="map">
	SELECT COUNT(*) num,t1.area,t2.dq_mc FROM opendata t1 INNER JOIN code_table_area t2 ON t1.area=t2.dq_dm GROUP BY t1.area ORDER BY num DESC LIMIT 5;
</select>
<select id="selectprovince" resultType="map">
    SELECT province,count(supplier_id) num FROM goods_supplier WHERE province IS NOT NULL GROUP BY province;
</select>
```

`Java`

> #### 拼接方式一

```java
	@Override
	public Map<String, Object> selectProvince() {


		List list = indexsMapper.selectprovince();
		Map<String, Object> map = new HashMap<>();
		StringBuilder chart = new StringBuilder();
		chart.append("[");
		for (int i = 0; i < list.size(); i++) {
			Map ln = (Map) list.get(i);
			String s;
			if (i != list.size() - 1) {
				s = "{\"name\":\"" + ln.get("province") + "\"," + "\"value\":" + ln.get("num") + "},";
			} else {
				s = "{\"name\":\"" + ln.get("province") + "\"," + "\"value\":" + ln.get("num") + "}";
			}

			chart.append(s);
		}
		chart.append("]");
		map.put("Province", chart);
        
        /**
        *{Province: "[{"name":"上海","value":2},{"name":"北京","value":6},{"name":"山	东","value":3},{"name":"重庆","value":5}]"}
        */
		return map;
	}
```

> #### 拼接方式二

```java
@Override
	public Map<String, Object> selectProvince() {

		List list = indexsMapper.selectprovince();

		// 字符串拼接，拼接成要求的JSON格式
		StringBuilder setName = new StringBuilder();
		StringBuilder setNum = new StringBuilder();
		setName.append("[");
		setNum.append("[");
		for (int i = 0; i < list.size(); i++) {
			// 省份名称 加双引号
			Map lnl = (Map) list.get(i);
			setName.append("\"");
			setName.append(lnl.get("province"));
			setName.append("\"");
			// 省份数量
			setNum.append(lnl.get("num"));
			// 加逗号，分割开
			if (i != list.size() - 1) {
				setName.append(",");
				setNum.append(",");
			}
		}
		setName.append("]");
		setNum.append("]");
		Map<String, Object> map = new HashMap<>();

		map.put("name", JSONArray.parse(setName.toString()));
		map.put("value", JSONArray.parse(setNum.toString()));

		/**
		 * 拼接之后的数据示例
		 *     var data = {
		 *         "name": ["北京", "天津", "上海", "重庆", "河北", "河南", "云南", "辽宁", "黑龙江", "湖南", "安徽", "山东", "新疆", "江苏", "浙江", "江西", "湖北", "广西", "甘肃", "山西", "内蒙古", "陕西", "吉林", "福建", "贵州", "广东", "青海", "西藏", "四川", "宁夏", "海南", "台湾", "香港", "澳门"],
		 *         "value": [2, 3, 4, 5, 6, 7, 8, 9, 1, 3, 1, 2, 3, 4, 5, 5, 6, 7, 8, 9, 4, 4, 3, 2, 1, 5, 6, 7, 8, 9, 3, 5, 6, 7]
		 *     };
		 */

		return map;
	}
```

