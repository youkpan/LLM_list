Explanation:

This interface adopts the same input and output format as openai, fully compatible with the openai interface, and can be adapted to your application by simply changing one line of code, so as to access a large number of open source projects, open source models, and faster and more cost-effective services. This interface does not include the knowledge base processing capability of the Exhibition Wisdom Assistant.

Interface format reference: [https://platform.openai.com/docs/api-reference/chat/object](https://platform.openai.com/docs/api-reference/chat/object)

API test page:

[https://ai.zyinfo.pro/](https://ai.zyinfo.pro/)

API access point: Please contact us on WeChat for OpenID.

Overseas node (faster, supports stream): [https://v.stylee.top:8899/llm_api/](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[{openid}/{userid}/{AI_system}](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[/v1/chat/completions](https://v.stylee.top:8899/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)

China (does not support native stream):

[https://ai.zyinfo.pro:8882/llm_api/](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[{openid}/{userid}/{AI_system}](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)[/v1/chat/completions](https://ai.zyinfo.pro:8882/llm_api/{openid}/{userid}/{AI_system}/v1/chat/completions)

API example: [https://v.stylee.top:8899/llm_api/](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)[test/test/qwen](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)[/v1/chat/completions](https://v.stylee.top:8899/llm_api/test/test/qwen/v1/chat/completions)

Method: POST

URL parameter description:

URL filling format interpretation: fixed part of the URL access point + openid / userid / AI_system / + v1/chat ...

openid: please contact us to create, WeChat youkpan. There are more discounts for large quantities.

userid: Please refer to [Exhibition Wisdom Assistant Knowledge Base AI Dialogue Interface](https://docs.qq.com/doc/DS0dWdmdNRkRWc2JJ) to create userid, or fill in any one.

AI_system: processing model (if AI_system is empty, the model parameter in POST json will be used. API access point: ...{userid}//v1/chat...) :

Support temprature, top_p, frequency penalty (default is 0) and other parameters, compatible with openai interface.

|AI_system<br>Processing Model|Model Name|Context|Price<br>Yuan/1K token|Chinese Ability|Explanation|
|:----|:----|:----|:----|:----|:----|
|gpt-3.5-turbo|ChatGPT<br>(for testing, not supported yet)|4K|0.042|Good|Usage limit|
|llama2-70b|LLama2 70B|4k|0.019|Average|Unlimited|
|qwen|Alibaba Qianwen2 72B|32k|0.04|Excellent|Unlimited|
|baichuan|Baichuan 53B|4k|0.04|Excellent|Limited, maximum 60 requests/min|
|llama2-32k|LLAMA2 7B|32K|0.0042|Poor|Unlimited|
|mistral|mistral 7B language model|4K|0.0042|Average|Unlimited, good 7B model. It is recommended to put the content in the first Message information. This model does not follow the instruction output.|
|misins|mistral chat 7B|4K|0.0042|Average|Unlimited, with instruction fine-tuning|
|misorca|mistral chat + orca 7B|8K|0.0042|Average|Unlimited, with instruction fine-tuning of large models, recommended for logical processing environment|
|misins-moe|Mixtral-8x7B Instruct expert model|32K|0.0084|Average|Unlimited, used for expert-level reasoning, with good effect|
|misins-moe2|Mixtral-8x7B Instruct<br>expert model 2|32K|0.0084|Average|Unlimited, third-party fine-tuning version, used for expert-level reasoning, GSM8k effect is average.|
|chat5-v|Visual model 5|8K|Calculated by processing time<br>0.015 yuan/S|Good|Unlimited, used for visual input processing. Before calling, please refer to the [uploadfile interface](https://docs.qq.com/doc/DS0dWdmdNRkRWc2JJ) to upload image streams and [instructions](https://docs.qq.com/doc/DS1RTcU1wRVJoRUhZ).|
|deepseek-coder-33b|Programming expert 33b|16K|0.017|Excellent|Unlimited, used for general software writing interaction, instruction interface|
|codellama-34b|Code LLama 34b Instruct|8K|0.017|Average|Unlimited, used for general software writing interaction, instruction interface|
|codellama-13b|Code LLama 13b Instruct|8K|0.0063|Average|Unlimited, used for general software writing interaction, instruction interface|
|vicuna-16k|vicuna 13b 16k|16K|0.0063|Average|Unlimited, used for longer context English processing|
|yi-34b|Yi 34b Chat|4K|0.011|Very good|Unlimited, used for longer context Chinese processing, shorter output content.|
|code3|Code expert model AIcoder 34B|16K|0.011|Average|Unlimited, used for code completion|
|pycode3|Code expert model AIcoder 34B|16K|0.012|Average|Unlimited, used for code completion, instruction fine-tuning|
|yi-34b-t|Yi 34b Chat|4K|0.019 yuan/S|Very good|Unlimited, used for longer context Chinese processing, shorter output content.|
|llama2-70b-t|llama2 70b for time fee|4K|0.019 yuan/S|Average|Unlimited, used for longer context English processing, shorter output content.|
|qwen-14b-t|qwen-14b-chat|8K|0.015 yuan/S|Very good|Unlimited|
|orca2-t|orca2 13B|4K|0.015 yuan/S|Average|Unlimited, good output logic|
|mistral-t|mistral 7B|8K|0.012 yuan/S|Average|Unlimited|
|misorca-t|mistral chat + orca 7B|8K|0.012 yuan/S|Average|Unlimited|
|misins-moe-t|Mixtral-8x7B Instruct expert model|32K|0.019 yuan/S|Average|Unlimited, used for expert-level reasoning, if the output is shorter, the cost is lower, and the effect is good|
|pycode3-t|python code expert model AIcoder 34b|16K|0.012 yuan/S|Average|Unlimited, used for code completion|
|pycode3.1-t|python code expert model AIcoder 34b|16K|0.016 yuan/S|Average|Unlimited, used for code completion|
|code3-t|Code expert model AIcoder 34B|16K|0.01 yuan/S|Average|Unlimited, used for code completion|
|code3.0-t|Code expert model AIcoder 34B|16K|0.01 yuan/S|Average|Unlimited, used for code completion|
|code3.1-t|Code expert model AIcoder 34B|16K|0.019 yuan/S|Average|Unlimited, used for code completion|
|code2-t|Code expert model AIcoder 15B|16K|0.016 yuan/S|Average|Unlimited, used for code completion|
|code2.1-t|Code expert model AIcoder 15B|16K|0.016 yuan/S|Average|Unlimited, used for code completion|
|phi2-t|Small model phi 2.7B|2K|0.0032 yuan/S|Average|Unlimited,|

● X yuan/S, represents billing based on processing time, used for processing longer context, shorter output content. However, for models that have not been requested for a long time or are not frequently used, it may be necessary to reload the model, which takes 3 to 5 minutes. The cost does not include the model loading period.

Interrupt the current generation by calling the interface:

API: APIendpoint + "/suspend_current_generate?openid=&userid="

Check your account balance:

[https://v.stylee.top:8882/api_user/info?openid=&type=](https://v.stylee.top:8882/api_user/info?openid=&type=)

Please complete the openid field, and the type can be json.

For example, for the test account test:

[https://ai.zyinfo.pro:8882/api_user/info?openid=test&type=](https://ai.zyinfo.pro:8882/api_user/info?openid=test&type=)

Privacy statement:

For companies with privacy concerns, we can help build a local deployment environment in the future. Except for legal requirements, we do not retain your content, make every effort to protect information security, do not involve your data in training, and employees have signed confidentiality agreements. Generally, employees do not have permission to view the processed content.

For access and obtaining openid, please contact us:

WeChat: youkpan

Email: youkpan@gmail.com

Shenzhen ZhanYing Information Technology [zyinfo.pro](http://zyinfo.pro)
