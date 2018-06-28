政企通-基础信息
修订历史
文档版本 更新时间 内容 作者 
1.0.0 2018-06-28 新建 廖文强 

服务边界设计
本系统边界和定位
本系统主要管理开发者、平台商户、收款商户的基础信息，将此功能向政企通的其它应用模块提供服务。

领域模型
操作员 
退款进度 
关键流程
对外服务
收款单位操作员登录
主要提供给OpenAPI进行调用，对开发者、平台商户调用接口的权限进行校验

调用方法
/operator/login

请求数据
域名 变量名 要求出现 备注 
收款商ID merchantId M  
操作员ID operatorId M  
密码 password O 平台商户不为空，会对平台商户的权限进行校验 

响应数据
域名 变量名 要求出现 备注 
校验结果 result M 0-登录失败 1-登录成功 

商户操作员-重置密码
调用方法
/operator/reset

请求数据
域名 变量名 要求出现 备注 
原密码 oldPassword M  
新密码 newPassword M  

响应数据
域名 变量名 要求出现 备注 
校验结果 result M 0-修改失败 1-修改成功 

日交易流水
调用方法
/trade/jour

请求数据
域名 变量名 要求出现 备注 
月份 month M  
交易状态 tradeStatus M  
页码 pageIndex M  
每页记录数 pageSize M  

响应数据
域名 变量名 要求出现 备注 
交易日期 tradeDate M  
交易总笔数 tradeNumber M  
交易总金额 tradeAmount M  

日交易明细
调用方法
/trade/detail

请求数据
域名 变量名 要求出现 备注 
交易日期 tradeDate M  
页码 pageIndex M  
每页记录数 pageSize M  

响应数据
域名 变量名 要求出现 备注 
下单时间 orderTime M  
平台商户订单号 merchantOrderNumber M  
平台流水号 orderNumber M  
交易金额 tradeAmount M  
支付时间 payTime M  
支付订单号 payOrderNumber M  
交易渠道 payChannel M  
支付结算日期 paySettleDate M  

日结算流水
调用方法
/settle/jour

请求数据
域名 变量名 要求出现 备注 
月份 month M  
页码 pageIndex M  
每页记录数 pageSize M  

响应数据
域名 变量名 要求出现 备注 
结算日期 settleDate M  
结算总笔数 settleNumber M  
结算总金额 settleAmount M  

日结算明细
调用方法
/settle/detail

请求数据
域名 变量名 要求出现 备注 
结算日期 tradeDate M  
页码 pageIndex M  
每页记录数 pageSize M  

响应数据
域名 变量名 要求出现 备注 
下单时间 orderTime M  
平台商户订单号 merchantOrderNumber M  
平台流水号 orderNumber M  
交易金额 tradeAmount M  
支付时间 payTime M  
支付订单号 payOrderNumber M  
交易渠道 payChannel M  
支付结算日期 paySettleDate M  

退款订单管理
调用方法
/refund/order

请求数据
域名 变量名 要求出现 备注 
退款申请日期 refundDate M  
审批状态 approvalStatus M  

响应数据
域名 变量名 要求出现 备注 
退款申请时间 refundApplyTime M  
退款订单号 refundOrderNumber M  
原订单号 oldOrderNumber M  
退款金额 refundAmount M  
审批状态 approvalStatus M  
退款状态 refundStatus M  
付款人 payer M  

退款订单详情
调用方法
/refund/details

请求数据
域名 变量名 要求出现 备注 
退款订单号 refundOrderNumber M  

响应数据
域名 变量名 要求出现 备注 
退款对象 refundObject M  
退款方式 refundWay M  
退款金额 refundAmount M  
退款进度 refundSchedule M  
退款申请时间 refundApplyTime M  
退款订单号 refundOrderNumber M  
原订单创建时间 oldOrderCreateTime M  
原订单号 oldOrderNumber M  
原订单金额 oldOrderAmount M  

商户信息
调用方法
/merchant/info

请求数据
域名 变量名 要求出现 备注 
平台商户Id merchantId M  

响应数据
域名 变量名 要求出现 备注 
平台商户Id merchantId M  
平台商户名称 merchantName M  
平台商户类型 merchantType M  
所在区划 division M  
行业 profession M  
所属开发者名称 developerName M  
所属开发者Id developerId M  
对应收款商户Id receiptMerchantId M  
对应收款商户名称 receiptMerchantName M  
有效期 contractStartAndEnd M  
状态 status M  
服务能力 ability M  

商户操作员管理
请求方法
/operator/manage

请求参数
域名 变量名 要求出现 备注 
操作员Id operatorId M  
页码 pageIndex M  
每页记录数 pageSize M  

响应参数
域名 变量名 要求出现 备注 
操作员Id operatorId M  
商户操作人员账号 operatorUserName M  
配置人员名称 operatorName M  
创建时间 createTime M  
状态 status M  

操作员状态启用/停用
请求方法
/operator/changeStatus

请求参数
域名 变量名 要求出现 备注 
当前状态 currentStatus M  

响应参数
域名 变量名 要求出现 备注 
结果 result M 0-状态修改失败 1-状态修改成功 

支付订单分析
请求方法
/pay/order/analyze

请求参数
域名 变量名 要求出现 备注 
支付日期 payDate M  

响应参数
域名 变量名 要求出现 备注 
订单金额 orderAmount M  
订单金额周同比 orderAmountWeekRatio M  
交易笔数 tradeNumber M  
交易笔数周同比 tradeNumberWeekRatio M  

订单金额趋势
请求方法
/orderAmount/trend

请求参数
域名 变量名 要求出现 备注 
支付日期区间 payDateInterval M  

响应参数
域名 变量名 要求出现 备注 
支付日期 date M  
订单金额 orderAmount M  

支付订单结算分析
请求方法
/pay/order/settleAnalyze

请求参数
域名 变量名 要求出现 备注 
结算日期 settleDate M  

响应参数
域名 变量名 要求出现 备注 
结算金额 settleAmount M  
结算金额周同比 settleAmountWeekRatio M  
结算笔数 settleNumber M  
结算笔数周同比 settleNumberRatio M  
结算成功率 settleSuccess M  
结算成功率周同比 settleSuccessWeekRatio M  
异常金额 exceptionAmount M  
异常金额周同比 exceptionAmountWeekRatio M  
异常笔数 exceptionNumber M  
异常笔数周同比 exceptionNumberWeekRatio M  

结算金额趋势
请求方法
/settleAmount/trend

请求参数
域名 变量名 要求出现 备注 
结算日期区间 settleDateInterval M  

响应参数
域名 变量名 要求出现 备注 
结算日期 settleDate M  
结算金额 settleAmount M  

