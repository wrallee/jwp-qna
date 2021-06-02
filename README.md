# JPA

## 요구사항

### Step1
 - [x] 아래의 DDL(Data Definition Language)을 보고 유추하여 엔티티 클래스와 리포지토리 클래스를 작성해 본다.
 - [x] @DataJpaTest를 사용하여 학습 테스트를 해 본다.
    ```sql
    create table answer
    (
        id          bigint generated by default as identity,
        contents    clob,
        created_at  timestamp not null,
        deleted     boolean   not null,
        question_id bigint,
        updated_at  timestamp,
        writer_id   bigint,
        primary key (id)
    )
   
   create table delete_history
   (
       id            bigint generated by default as identity,
       content_id    bigint,
       content_type  varchar(255),
       create_date   timestamp,
       deleted_by_id bigint,
       primary key (id)
   )
   
   create table question
   (
       id         bigint generated by default as identity,
       contents   clob,
       created_at timestamp    not null,
       deleted    boolean      not null,
       title      varchar(100) not null,
       updated_at timestamp,
       writer_id  bigint,
       primary key (id)
   )
   
   create table user
   (
       id         bigint generated by default as identity,
       created_at timestamp   not null,
       email      varchar(50),
       name       varchar(20) not null,
       password   varchar(20) not null,
       updated_at timestamp,
       user_id    varchar(20) not null,
       primary key (id)
   )
   
   alter table user
       add constraint UK_a3imlf41l37utmxiquukk8ajc unique (user_id)
    ```