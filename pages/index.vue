<template>
  <div class="grid grid-rows-layout h-screen">
    <Header />
    <main class="container mx-auto py-8">
      <section id="top" class="mb-12">
        <Card>
          <template #title>
            プログラミングは人生の一部
          </template>
          <template #content>
            <p class="mt-4">プログラミングは人生の一部。昔、異業種への転職も含めて考えていた時に親友からスマホアプリ開発の話を受けました。 調べならが徐々にできて行くアプリに楽しさを覚え、それ以来プログラミングが楽しい事、私の人生の一部になりました。 そんな気持ちをサブタイトルに込めています。</p>
          </template>
        </Card>
      </section>

      <section id="about" class="mb-12">
        <Card>
          <template #title>自己紹介</template>
          <template #content>
            <p class="mt-4">工業高校時代にインターネットにのめり込み、卒業後プログラマとしてキャリアを開始。 初めて業務で先輩から教えてもらった言語はC言語。 その後、外資系半導体企業からSIerへ転職し、主にJava, Perl, MFCを業務で使用。2018年中旬にメーカ系企業に転職し主にフロントエンド(PHP, Vue)を担当。 趣味は、バイクでのツーリング。月一回、仲間と関西周辺を走りに行っている。</p>
          </template>
        </Card>
      </section>

      <section id="skill" class="mb-12">
        <Card>
          <template #title>
            <h2 class="text-2xl font-bold">スキル</h2>
          </template>
          <template #content>
            <div class="">
              <template v-for="skill in skills" :key="skill.title">
                <SkillCard class="mb-4" :title="skill.title" :description="skill.description" :useYear="skill.useYear" />
              </template>
            </div>
          </template>
        </Card>
      </section>

      <section id="content" class="mb-12">
        <Card>
          <template #title>コンテンツ</template>
          <template #content>
            <ul class="mt-4">
              <li><strong>ニコカレ - ニコニコカレンダー</strong>: 友人の仕事がきっかけで作成したアプリ。メンテナンスをサボっていたため削除された。リンクは過去に残っていた紹介ページ。</li>
              <li><strong>Bun-chan-bot</strong>: ラズパイを使いたいというのと、日中部屋を留守にするのでモニタリングするために作成。</li>
            </ul>
          </template>
        </Card>
      </section>
    </main>

    <footer class="bg-gray-800 text-white py-4">
      <div class="container mx-auto flex justify-center space-x-4">
        <Button label="GitHub" class="p-button-text" />
        <Button label="Facebook" class="p-button-text" />
        <Button label="Instagram" class="p-button-text" />
        <Button label="Qiita" class="p-button-text" />
        <Button label="X" class="p-button-text" />
      </div>
    </footer>
  </div>
</template>

<script setup>

const skills = ref([
  { title: 'Java', description: '業務系アプリのバックエンド開発。Oracle, MySQL, PostgreSQL を使用。J2EE を用いた API 構築で Guava や JUnit を活用。', useYear: 5 },
  { title: 'C, MFC', description: '解析アプリケーションの保守で使用。C#と接続するためにCRLを使ったりもしていた。', useYear: 3 },
  { title: 'PHP, Vue', description: 'フロントエンド開発の主担当（PHP:2割, Vue:8割）。直近は、新規プロダクトの設定画面構築に携わり、ライブラリ選定、設計、実装を担当。使用技術: ESLint, Prettier, Vue3, vee-validate, zod, ky', useYear: 6 },
  { title: 'Perl', description: '半導体企業でのテキスト操作で使用。現在も特定のタスクで活用。', useYear: 5 },
  { title: 'Python', description: 'Django を使った WebAPI プロトタイプ作成や、個人プロジェクト（Twitter Bot）で使用。', useYear: 1 },
]);

import Header from '/components/Header.vue';
import SkillCard from '/components/SkillCard.vue';
</script>

<style>
html {
  scroll-behavior: smooth;
}
section[id] {
  scroll-margin-top: 5rem;
}
</style>

<style scoped>
body {
  font-family: 'Inter', sans-serif;
}

.grid-rows-layout {
  display: grid;
  grid-template-rows: auto 1fr auto;
}
</style>
