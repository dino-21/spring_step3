
spring_step3

3tier_jsp_crud_6


![45](https://github.com/dino-21/3tier_jsp_crud_6/assets/80396471/76246318-ac99-4971-88d5-b14294471005)


![11](https://github.com/dino-21/3tier_jsp_crud_6/assets/80396471/6bf2c466-4921-4703-9f6a-a6ca92fc3030)


![24](https://github.com/dino-21/3tier_jsp_crud_6/assets/80396471/7c25eaac-52b2-4f5a-a9c6-11fb8c2bbc48)


![40](https://github.com/dino-21/3tier_jsp_crud_6/assets/80396471/4bdbf20c-2002-4244-9983-beb528d7cdf0)



1. SampleController.java 코드 수정 – list 추가
@GetMapping("/list")
코드 추가


2.  list.jsp파일 만들기
${list} 값오는지 확인


3. 부트스크랩4의 table가져와서 
list.jsp  코드 수정
jstl 라이브러리 추가
<c:forEach>문에
${list.id}
${list.title}
${list.content}
브라우저에서 리스트 확인하기


4. 리스트에서 제목 클릭하면 해당 파라미터로 가게 확인
    <td><a href="/read?id=${list.id}">${list.title}</a></td>


5. 부트스크랩4 읽기 form 가져오기
read.jsp  코드 수정

<input type="text " id="id" value="${list.id}" name="id" readonly="readonly">
<input type="text " id="title"  value="${list.title}"  name="title">
<input type="text " id="content"  value="${list.content}" name="content">
<button> onclick="window.location.href='list'">List</button>
리스트에서 제목 클릭해서 read.jsp로 param 값이 가는지 확인
http://localhost:8282/list  
http://localhost:8282/read?id=6



6.  SampleController.java 코드 수정 - update
@PostMapping("/update") 


7. 글을 수정하고 업데이트 하면 한글이 깨짐

8. web.xml 파일에서 한글깨짐 필터 적용하기

9. 한글깨짐 필터 적용후 
리스트에서 한글 수정하고 update 버튼 눌러서
한글 안깨지는 확인


10. read.jsp에서 delete 버튼을 클릭하려면 
라우터를 /delete해줘야 하고
form의 이름을 다른게 해줘야 해서 자바스크립트 코드가 필요함


11 SampleController.java 코드 수정 - delete
@PostMapping("/delete")


12.  insert 준비
list.jsp 코드 수정 - insert 버튼 추가 


13. insert.jsp 페이지 만들기만들기


14. SampleController.java 코드 수정 - insert
@GetMapping("/insert")
@PostMapping("/insert")


15. list.jsp 페이지에<h3>${msg}</h3> 코드추가
 insert, update, delete 할 경우 메시지 보이게 준비

16.   SampleController.java 코드 수정 –  insert, update, delete 할 경우 메시지 보이게
(RedirectAttributes redirectAttributes)
redirectAttributes.addFlashAttribute("msg", "등록이 완료되었습니다.");
