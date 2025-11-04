# 鸿蒙工具集 - 核心基础工具包

## 简介
`@lh/study_core` 是鸿蒙工具集的核心基础模块，为 HarmonyOS Next 应用开发提供轻量、高效、符合规范的基础工具集。模块完全使用 ArkTS（TypeScript 超集）开发，严格遵循 HarmonyOS HAR（HarmonyOS Ability Resource）包规范，可无缝集成到任何 HarmonyOS Next 项目中。

**核心特性**:
- ✅ **零外部依赖**：不依赖任何第三方库，可独立使用，避免依赖冲突；
- ✅ **类型安全**：提供完整的 TypeScript/ArkTS 类型定义，支持代码提示与静态检查；
- ✅ **文档完善**：每个方法均包含详细 JSDoc 注释（含参数、返回值说明）及使用示例；
- ✅ **规范遵循**：严格符合 HarmonyOS HAR 包结构规范，适配 DevEco Studio 开发流程；
- ✅ **质量保障**：覆盖核心功能的单元测试（测试覆盖率 ≥ 90%），确保稳定性；
- ✅ **性能优化**：针对 HarmonyOS 平台特性优化，如轻量计算、异步任务调度等。

## 安装指南
1. 通过 ohpm 安装（推荐）
2. 使用 HarmonyOS 官方包管理工具 ohpm 快速安装：

```bash
1. ohpm install @lh/study_core
```

## 打开项目根目录下的 oh-package.json5（或 package.json，以项目实际配置为准）；
### 在 dependencies 节点中添加依赖：

```Json5
{
  "dependencies": {
    "@mxu/toolkit_core": "^1.0.0"
  }
}
```

```typescript
import { StringUtils, DateUtils, DeviceInfo } from '@lh/study_core';


   TypeScript
   // 生成 UUID（v4 版本）
   const uuid = StringUtils.generateUUID();
   console.log(uuid); // 输出："55e8e4b0-e29a-4104-a716-4466554a688b"

// 验证邮箱格式（支持国际域名）
const isEmailValid = StringUtils.isEmail('test.123@example.com.cn');
console.log(isEmailValid); // 输出：true

// 手机号掩码（保留前3位+后4位）
const maskedPhone = StringUtils.maskPhone('13812345678');
console.log(maskedPhone); // 输出："138****5678"

   TypeScript
   // 格式化日期（自定义格式）
   const now = new Date();
   const formattedDate = DateUtils.format(now, 'yyyy-MM-dd HH:mm:ss');
   console.log(formattedDate); // 输出："2025-11-04 17:30:00"

// 计算相对时间（如「1小时前」「3天前」）
const oneHourAgo = new Date(Date.now() - 3600 * 1000);
const relativeTime = DateUtils.fromNow(oneHourAgo);
console.log(relativeTime); // 输出："1小时前"
  
   TypeScript
   // 获取设备型号（如「P60 Pro」）
   const deviceModel = DeviceInfo.getModel();
   console.log(deviceModel); // 输出："HarmonyOS Device Model"

```
