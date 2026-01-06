# Git Flow Process
1. Git commands:
  - git pull: Để kéo các thay đổi mới từ branch khác về branch hiện tại.
  - git push: Để đẩy các thay đổi mới từ branch hiện tại lên 1 branch.
  - git merge: Để trộn các thay đổi từ 1 branch khác với branch hiện tại.
  - git cherry-pick: Để lấy 1 hoặc 1 vài commit từ branch khác về branch hiện tại.
  - git rebase: Để đưa commit của branch hiện tại lên HEAD của branch khác.
  - git reset: Để di chuyển HEAD về commit cũ hơn.
2. Basic git flow:
  - Gitflow là một ý tưởng trừu tượng về quy trình sử dụng Git, nó chỉ ra cách thức setup các loại branchs khác nhau và cách thức để merge chúng lại với nhau.
  - Master: branch chứa mã nguồn khởi tạo của ứng dụng và các version đã sẵn sàng để realease cho người dùng có thể sử dụng.
  - Hotfix: Được base trên nhánh master để sửa nhanh những lỗi trên UIT hoặc sửa những cấu hình đặc biệt chỉ có trên môi trường productions.
  - Release: Trước khi Release một phần mềm dev team cần được tạo ra để kiểm tra lại lần cuối trước đi release sản phần để người dùng có thể sử dụng
  - Develop: Được khởi tạo từ master branch để lưu lại tất cả lịch sử thay đổi của mã nguồn. Develop branchs là merge code của tất cả các branchs feature.
  - Feature: Được base trên branch develop. Mỗi khi phát triển một feature mới chúng ta cần tạo một branchs để viết mã nguồn cho từng feature.
3. Git Structure Monolith, Multirepo, Monorepo
  - Monolith: Một ứng dụng duy nhất, các module gắn chặt, build & deploy cùng nhau.
  - Multirepo: Một ứng dụng như chia nhiều repo khác nhau cho từng chức năng hoặc project (FE, BE, ...)
      + Props: Dễ cho access control, build và deploy, scalability.
      + Cons: Phải setup cho thư viện,... cho từng repo, dễ dẫn tới xung đột.
  - Monorepo: Một ứng dụng sử dụng chung 1 repo duy nhất để quản lý
      + Props: Dễ cho dùng chung thư viện, components, utility giữa các dự án. Tất cả dự án đều dùng chung thư viện.
      + Cons: Repo sẽ phình to khi dự án càng lớn: khiến clone, pull,status lâu. CI/CD phức tạp, cần tool hỗ trợ, khó access control
