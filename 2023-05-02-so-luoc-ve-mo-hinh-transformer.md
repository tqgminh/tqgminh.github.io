---
layout: post
title: "SƠ LƯỢC VỀ MÔ HÌNH TRANSFORMER"
author: "Minh Tran"
categories: knowledge
tags: [knowledge]
image: Transformer/cover.jpg
---

Nhắc đến Transformer, có lẽ người ta sẽ liên tưởng ngay đến series phim điện ảnh bom tấn về người máy của "ông hoàng cháy nổ " Michael Bay. Tuy nhiên, với những ai làm việc trong lĩnh vực Trí tuệ nhân tạo (AI) thì đây là một thuật ngữ chuyên ngành, là tên của một mô hình rất quan trọng và đột phá của lĩnh vực này. Transformer được giới thiệu lần đầu trong bài báo Attention Is All You Need tại hội thảo NeurIPS năm 2017 bởi một nhóm nghiên cứu của Google. Kể từ đây, nó đã thay đổi hoàn toàn bộ mặt của ngành AI, đặc biệt là lĩnh vực Xử lý ngôn ngữ tự nhiên (NLP). Dựa trên Transformer, hàng loạt các mô hình ngôn ngữ lớn được ra đời, với kích thước từ vài chục triệu cho đến hàng trăm tỉ tham số, kéo theo đó là kết quả ngày một cải thiện cho mọi bài toán. Thực tế thì sau khi Transformer ra đời, đã có rất nhiều nghiên cứu cải tiến các thành phần trong mô hình này để nó tối ưu hơn cả về kết quả cũng như thời gian, bộ nhớ huấn luyện. Tuy nhiên trong bài viết này, mình sẽ chỉ trình bày về các thành phần của mô hình Transformer được đề xuất trong bài báo gốc, trong giới hạn mà mình tìm hiểu được.

## Tổng quan mô hình

### Nhắc lại về Sequence-to-sequence

Đúng như tên gọi, Sequence-to-sequence (Seq2Seq) có nhiệm vụ nhận vào một chuỗi, ký hiệu là $$\textbf{x}$$ để sinh ra một chuỗi mới, ký hiệu là $$\textbf{y}$$. Mô hình này thường được ứng dụng rất nhiều để giải quyết các bài toán NLP. Chẳng hạn với bài toán dịch máy