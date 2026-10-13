# AI Agent Software Development Blueprint — Local Restaurant System

Bộ khung khởi đầu để một solo developer dùng AI coding agents xây hệ thống quản lý nhà hàng từ đầu, theo hướng specification-first, làm từng lát nhỏ và kiểm chứng được.

> **Trạng thái hiện tại:** Đây là template, không phải một bản thiết kế đã được phê duyệt. Không xem các ví dụ hoặc lựa chọn mặc định là quyết định cuối cùng nếu chưa được ghi vào tài liệu `DECIDED`/ADR.

## Bối cảnh ban đầu

Các thông tin này là giả định dựa trên mô tả hiện có và cần xác minh ở `docs/00-product-brief.md`:

- Một nhà hàng, một địa điểm.
- Chạy nội bộ tại nhà hàng, chưa có domain/hosting.
- Một máy tính quản lý và in hóa đơn.
- Khách có thể quét QR tại bàn để xem menu và gọi món.
- Lượng khách vừa phải; nhiều điện thoại có thể gửi order cùng lúc.
- Máy tính và điện thoại khách dự kiến dùng chung Wi-Fi/LAN; phải xác minh router có bật client isolation hay không.
- Chưa chốt stack, loại máy in, nền tảng hệ điều hành, database, workflow bếp, thanh toán hoặc quản lý kho.

## Cách dùng

1. Đưa nội dung thư mục này vào một repository Git riêng.
2. Đọc và hoàn thành `docs/00-product-brief.md`; ghi câu hỏi còn thiếu vào `docs/15-open-questions-and-risks.md`.
3. Chạy lần lượt các prompt trong `prompts/`. Mỗi prompt yêu cầu AI làm một phase, không làm tất cả cùng lúc.
4. Giữ nhãn trạng thái rõ ràng: `OPEN`, `PROPOSED`, `DECIDED`, `DEFERRED`.
5. Chỉ chuyển tài liệu sang `DECIDED` khi người sở hữu sản phẩm đã duyệt. Ghi quyết định kiến trúc quan trọng vào `docs/adr/`.
6. Chỉ mở coding phase khi đã chốt scope MVP, flow chính, rules quan trọng, architecture, data model, API contract cần thiết và acceptance criteria.
7. Mỗi task code phải có phạm vi, file/module dự kiến, kiểm tra và Definition of Done. Làm một vertical slice nhỏ, chạy test, review, rồi mới nhận task kế tiếp.

## Cổng kiểm soát (gates)

### Gate A — Problem & scope
- [ ] Người dùng và vấn đề thực tế được xác nhận.
- [ ] MVP / Later / Out of scope được phân biệt.
- [ ] Open questions có owner hoặc được chấp nhận là giả định tạm thời.

### Gate B — Behavior
- [ ] Luồng QR gọi món → nhân viên/bếp xử lý → thanh toán/in hóa đơn được mô tả.
- [ ] Vòng đời order/table/payment được mô tả bằng trạng thái và chuyển trạng thái hợp lệ.
- [ ] Các rule về giá, hủy món, món hết hàng, gửi bếp và thanh toán được duyệt.
- [ ] Acceptance criteria có thể kiểm thử.

### Gate C — Technical contracts
- [ ] Kiến trúc phù hợp với triển khai LAN được duyệt.
- [ ] Data model và migration strategy được duyệt.
- [ ] API contract được chốt cho vertical slice đầu tiên.
- [ ] Chiến lược test, bảo mật, backup/restore và logging được xác định.
- [ ] Máy in/driver/protocol và khả năng truy cập từ điện thoại đã được thử nghiệm sớm hoặc có spike task rõ ràng.

### Gate D — Ready to code
- [ ] Repo có hướng dẫn agent ngắn gọn và các lệnh build/test thật.
- [ ] CI hoặc ít nhất một lệnh kiểm tra tái lập được.
- [ ] Task đầu tiên đủ nhỏ và có Definition of Done.

## Kiến trúc triển khai cần nghiên cứu

Một phương án để đánh giá (chưa phải quyết định): máy tính tại nhà hàng chạy web application/backend và database; điện thoại mở trang QR qua IP/hostname nội bộ và gọi backend qua HTTP trên LAN; phần in hóa đơn chạy trên máy tính hoặc print service nội bộ. Không đưa database ra chia sẻ file qua Wi-Fi, và không để trình duyệt điện thoại kết nối trực tiếp với DB.

Cần thử nghiệm sớm: địa chỉ IP cố định/reservation, firewall, Wi-Fi client isolation, nhiều order đồng thời, browser trên điện thoại, mất mạng LAN, máy in mất kết nối, backup và khôi phục. Nếu cân nhắc SQLite, hiểu rõ cách triển khai: SQLite WAL không dùng được trên network filesystem. Xem tài liệu chính thức: https://www.sqlite.org/wal.html

## Cấu trúc chính

```text
AGENTS.md                  # Quy tắc agent ở cấp repo
CLAUDE.md                  # Wrapper nhỏ cho Claude Code
.github/copilot-instructions.md

docs/
  00-product-brief.md
  01-domain-discovery.md
  02-mvp-scope.md
  03-user-flows.md
  04-requirements.md
  05-business-rules.md
  06-edge-cases.md
  07-domain-model.md
  08-architecture.md
  09-security-and-privacy.md
  10-api-contract.md
  11-test-strategy.md
  12-deployment-runbook.md
  13-task-backlog.md
  14-definition-of-done.md
  15-open-questions-and-risks.md
  adr/ADR-TEMPLATE.md
  templates/FEATURE-SPEC-TEMPLATE.md
  templates/TASK-TEMPLATE.md
prompts/
  01-discover-domain.md
  02-define-mvp-and-requirements.md
  03-map-flows-and-rules.md
  04-challenge-and-gap-analysis.md
  05-design-architecture-and-contracts.md
  06-plan-a-vertical-slice.md
  07-implement-approved-task.md
  08-review-and-test.md
  09-deployment-readiness.md
```

## Tài liệu nguồn tham khảo

- AGENTS.md: https://agents.md/
- Codex prompting guide: https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide
- GitHub Copilot custom instructions: https://docs.github.com/en/copilot/reference/custom-instructions-support
- Claude Code memory/CLAUDE.md: https://docs.anthropic.com/en/docs/claude-code/memory
- OpenAPI Specification: https://spec.openapis.org/oas/
- SQLite WAL: https://www.sqlite.org/wal.html
- OWASP ASVS: https://owasp.org/projects/asvs

Kiểm tra lại tài liệu chính thức tại thời điểm sử dụng vì hỗ trợ instruction files và phiên bản công cụ có thể thay đổi.
