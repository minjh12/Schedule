# Schedule

![image](https://github.com/user-attachments/assets/4a57dda2-93e3-4aa5-864e-b54dabce401d)

API명세서와 관련 코드입니다.

```package com.sparta.schedule.controller;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.ResponseBody;
@Controller
@RequestMapping("/api")
public class ScheduleController {

    // 일정 작성하기 (경로는 유지)
    @GetMapping("/schedule")
    @ResponseBody
    public String post() {
        return "일정 작성하기";
    }

    // 선택 일정 조회하기
    @GetMapping("/schedule/view")
    @ResponseBody
    public String getSchedule(@RequestParam("scheduleId") String scheduleId) {
        return "선택 일정 조회하기: " + scheduleId;
    }

    // 전체 일정 조회하기 (추가적인 필터링을 요청 파라미터로 받을 수 있음)
    @GetMapping("/schedule/all")
    @ResponseBody
    public String getAllSchedules(@RequestParam(value = "filter", required = false) String filter) {
        if (filter != null) {
            return "필터링된 일정 조회: " + filter;
        }
        return "전체 일정 조회하기";
    }

    // 일정 삭제하기
    @GetMapping("/schedule/delete")
    @ResponseBody
    public String deleteSchedule(@RequestParam("scheduleId") String scheduleId) {
        return "일정 삭제하기: " + scheduleId;
    }

    // 일정 수정하기
    @GetMapping("/schedule/edit")
    @ResponseBody
    public String updateSchedule(@RequestParam("scheduleId") String scheduleId) {
        return "일정 수정하기: " + scheduleId;
    }
}
```



![스크린샷(39)](https://github.com/user-attachments/assets/d9f63683-16a3-4845-9efa-a59b1bf19a8c)


