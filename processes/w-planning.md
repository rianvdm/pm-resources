## Planning using the W Framework

[The original article](https://review.firstround.com/the-secret-to-a-great-planning-process-lessons-from-airbnb-and-eventbrite) on the W Planning does an excellent job of explaining the framework, and it should definitely be on your reading list. Below is a short summary of how I prefer to use the framework. The gist is that planning is most effective when it is a collaborative effort between Leadership (senior/executive leaders of a business unit) and Teams (people delivering the actual work). This makes it a particularly appropriate framework for empowered and autonomous teams. The framework looks like this:

![](https://files.elezea.com/W_Framework.jpg)

The four stages are described as follows in the article:

> **Context**: Leadership shares a high-level strategy with Teams.
> 
> **Plans**: Teams respond with proposed plans.
> 
> **Integration**: Leadership integrates into a single plan, and shares with Teams.
> 
> **Buy-in**: Teams make final tweaks, confirm buy-in, and get rolling.

So when I go into our planning cycles I like to use W planning to come up with our tasks for the period.

### Phase 1: Context

As a leadership team we review our annual and quarterly goals as laid out in our corporate and product strategy, and make sure we are still focused on the right things. We ensure that the entire team has the strategic context they need to successfully enter the planning phase.

### Phase 2: Plans

Teams take the goals and strategic context, and create project plans as bets on how they would like to achieve those goals. Note that at this point the “Tasks for the period” aren’t defined yet—that comes from the teams based on how they believe we can achieve our stated goals. [In the words of Father Cagan](https://techleadjournal.dev/episodes/102/):

> Instead of being given a roadmap of features, an empowered team is given a problem to solve and they get to figure out the best way to solve that problem.

I like to use a specific Project Plan template for this part, which [you can see here](https://github.com/rianvdm/pm-resources/blob/main/templates/product-plan.md). The plan does not have to have every detail figured out. We view it as “[a road sign into the fog](https://elezea.com/2023/03/product-management-and-the-fog-of-war/).” We make sure the direction and first few steps are known, then add and edit as the fog starts clearing down the road.

We then share the plan with everyone in the [DACI section](https://github.com/rianvdm/pm-resources/blob/main/processes/daci.md) of the plan by posting a link and requesting feedback form the team. We discuss comments asynchronously in Google Docs, or synchronously on a Zoom call if a decision can't be made quickly in the comments.

### Phase 3: Integration

Once the team planning phase is done the leadership team gets together again to discuss the plans, how it all fits together, and any trade-offs that need to be made. This is where we decide on the task for the period and make sure we are not taking on too much work for the time we have.

### Phase 4: Buy-in

As a team we then get together to finalize the project plans, discuss any final questions/feedback on our priorities, and move individual tasks to Basecamp/Asana/wherever (for non-dev projects) or the appropriate Jira/Linear Epics (for dev projects).

Once we finish this process our teams are ready to execute on their projects with clarity on how each project aims to influence our goals. This includes essential engineering scaling and reliability work—for instance, if our goal is to significantly increase the number of messages sent, we're going to have to make sure that the platform can scale with that.