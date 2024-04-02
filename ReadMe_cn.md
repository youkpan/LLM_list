说明：

	本接口采用与openai同样格式的输入输出方式，完全兼容 openai 接口，适配你的应用程序，只需要改动一行代码，即可接入大量开源项目、开源模型和接入更快、更高性价比的服务。本接口不包含展映智慧助手的知识库处理能力。

	接口格式参考：[https://platform.openai.com/docs/api-reference/chat/object](https://platform.openai.com/docs/api-reference/chat/object)

API 测试页面：

[https://ai.zyinfo.pro/](https://ai.zyinfo.pro/)

API 接入点：OpenID获取请联系我们微信 youkpan。

海外节点（更快,支持stream ）：[https://v.stylee.top:8899/llm_api/](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[{openid}/{userid}/{AI_system}](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[/v1/chat/completions](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)

国内（不支持原生stream）：

[https://ai.zyinfo.pro:8882/llm_api/](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[{openid}/{userid}/{AI_system}](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[/v1/chat/completions](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)

API示例：[https://v.stylee.top:8899/llm_api/](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)[test/test/qwen](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)[/v1/chat/completions](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)

方法：POST

URL参数说明：

URL 填充格式解释：URL接入点固定部分 + openid / userid / AI_system /+ v1/chat ...

openid : 请联系我们创建，微信 youkpan。用量大还有更多折扣。

userid：请参考 [展映智慧助手知识库AI对话接口](https://docs.qq.com/doc/DS0dWdmdNRkRWc2JJ) 创建userid ，或者任意填一个。

AI_system:处理模型（若 AI_system 为空，则采用 POST  json中的model参数。API 接入点：...{userid}//v1/chat... ）:

支持 temprature, top_p ,频率惩罚（默认为0）等参数，与openai接口兼容。

|AI_system<br>处理模型| 模型名称|上下文|价格<br>元/1K token|中文能力|说明|
|:----|:----|:----|:----|:----|:----|
|gpt-3.5-turbo|ChatGPT<br>（测试用，暂不支持）|4K|0.042|良好|有使用量限制|
|llama2-70b|LLama2 70B|4k|0.019|一般|不限量|
|qwen|阿里千问2 72B|32k|0.04|优秀|不限量|
|baichuan|百川 53B|4k|0.04|优秀|限量，请求速率最多60个请求/min|
|llama2-32k|LLAMA2 7B|32K|0.0042|较差|不限量|
|mistral|mistral  7B<br>语言模型|4K|0.0042|一般|不限量，较好的7B 模型。建议内容放到第一个Message信息。该模型不遵循指令输出。|
|misins|mistral chat 7B|4K|0.0042|一般|不限量，加入指令微调|
|misorca|mistral chat +orca 7B|8K|0.0042|一般|不限量，加入大模型的指令微调，推荐用于逻辑处理环境|
|misins-moe|Mixtral-8x7B Instruct 专家模型|32K|0.0084|一般|不限量，用于专家级推理，效果较好|
|misins-moe2|Mixtral-8x7B Instruct <br>专家模型 2|32K|0.0084|一般|不限量，第三方微调版本，用于专家级推理，GSM8k效果一般。|
|chat5-v|视觉模型 5|8K|按处理时间算<br>0.015元/S|较好|不限量，用于视觉输入处理。调用前，请参考[uploadfile 接口](https://docs.qq.com/doc/DS0dWdmdNRkRWc2JJ)上传图像流，及[说明](https://docs.qq.com/doc/DS1RTcU1wRVJoRUhZ)。|
|deepseek-coder-33b|编程专家33b|16K|0.017|优秀|不限量，用于通用的软件编写交互，指令接口|
|codellama-34b|Code LLama 34b Instruct|8K|0.017|一般|不限量，用于通用的软件编写交互，指令接口|
|codellama-13b|Code LLama 13b Instruct|8K|0.0063|一般|不限量，用于通用的软件编写交互，指令接口|
|vicuna-16k|vicuna 13b 16k|16K|0.0063|一般|不限量，用于较长上下文的英文处理|
|yi-34b|Yi 34b Chat|4K|0.011|很好|不限量，用于较长上下文的中文处理，较短的输出内容。|
|code3|代码专家模型 AIcoder  34B |16K|0.011|一般|不限量，用于代码补全|
|pycode3|代码专家模型 AIcoder  34B |16K|0.012|一般|不限量，用于代码补全，指令微调|
|yi-34b-t|Yi 34b Chat|4K|0.019元/S|很好|不限量，用于较长上下文的中文处理，较短的输出内容。|
|llama2-70b-t|llama2 70b for time fee|4K|0.019元/S|一般|不限量，用于较长上下文的英文处理，较短的输出内容。|
|qwen-14b-t|qwen-14b-chat|8K|0.015元/S|很好|不限量|
|orca2-t|orca2 13B|4K|0.015元/S|一般|不限量，较好的输出逻辑|
|mistral-t|mistral 7B|8K|0.012元/S|一般|不限量|
|misorca-t|mistral chat +orca 7B|8K|0.012元/S|一般|不限量|
|misins-moe-t|Mixtral-8x7B Instruct 专家模型|32K|0.019元/S|一般|不限量，用于专家级推理，若输出较短内容，成本更低，效果较好|
|pycode3-t|python 代码专家模型 AIcoder  34b |16K|0.012元/S|一般|不限量，用于代码补全|
|pycode3.1-t|python 代码专家模型 AIcoder  34b |16K|0.016元/S|一般|不限量，用于代码补全|
|code3-t|代码专家模型 AIcoder  34B |16K|0.01元/S|一般|不限量，用于代码补全|
|code3.0-t|代码专家模型 AIcoder  34B |16K|0.01元/S|一般|不限量，用于代码补全|
|code3.1-t|代码专家模型 AIcoder  34B |16K|0.019元/S|一般|不限量，用于代码补全|
|code2-t|代码专家模型 AIcoder  15B |16K|0.016元/S|一般|不限量，用于代码补全|
|code2.1-t|代码专家模型 AIcoder  15B |16K|0.016元/S|一般|不限量，用于代码补全|
|phi2-t|小模型 phi  2.7B |2K|0.0032元/S|一般|不限量，|

● X 元/S ,代表按处理时长计费，用于较长上下文的处理，较短的输出内容。但长时间没有请求或不常用的模型，可能需要重新加载模型，时间为3~5分钟。模型载入期间不计入费用。

接入示例 python 使用官方库：

pip install openai

from openai import OpenAI

import os

openid="test"

userid="test"

AI_system="qwen"

#api_base "https://v.stylee.top:8899/test/test/qwen/v1"

#api_key 可以是一个伪造的key

api_base = f"https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1"

client = OpenAI(

    base_url=api_base,

    api_key="sk-ppV31ZNgxR1tngpIsej0T1BlbkF32c2QeWo74vDXKpaswfTY")

res = client.chat.completions.create(

      model=AI_system,

      messages=[

        {"role": "system", "content": "You are a helpful assistant."},

        {"role": "user", "content": "hello,what is 1-1=?"}

      ],

      stream= False,

    )

print(res)

print(res.choices[0].message.content)

#stream 测试

for chunk in  client.chat.completions.create(

      model=AI_system,

      messages=[

        {"role": "system", "content": "You are a helpful assistant."},

        {"role": "user", "content": "hello,1-1=?"}

      ],

      stream= True,

    ):

    #print(chunk)

    if len(chunk.choices)>0:

        content = chunk.choices[0].delta.content

        if content is not None:

            print(content, end='', flush=True)


中断当前生成请调用 接口：

	API: APIendpoint + "/suspend_current_generate?openid=&userid="

查看你的账户额度：

[https://v.stylee.top:8882/api_user/info?openid=&type=](https://v.stylee.top:8882/api_user/info?openid=&type=)

请补齐openid 字段，type 可为 json。

例如 测试账号 test：

[https://ai.zyinfo.pro:8882/api_user/info?openid=test&type=](https://ai.zyinfo.pro:8882/api_user/info?openid=test&type=)

隐私说明：

	有隐私顾虑的企业，未来我们可以帮助搭建本地的部署环境。除法规需要，我们不保留您的内容，尽全力保护信息安全，不将您的数据参与训练，员工已签保密协议，处理的内容一般员工无权限查看到。

	

接入及获取openid 请联系我们：

微信 ：youkpan

Email: youkpan@gmail.com

深圳展映科技 [zyinfo.pro](http://zyinfo.pro)


