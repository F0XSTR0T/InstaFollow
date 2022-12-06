# InstaFollow

## React Component à réprendre en supprimant le Ban IP et les CORS Policy
```
import React, { useEffect, useState } from 'react';
import axios from 'axios';


const Insta = () => {

    const [data, setData] = useState([]);


    useEffect(() => {
        axios.get("https://www.instagram.com/f0xs_trot/?__a=1&__d=dis")
        .then((res) => setData(res.data))
    }, [])

    return (
        <div className="followersInsta">
            <ul>
                {
                    data.map((follow) => <p>{follow.graphql.user.edge_followed_by}</p>)
                }
            </ul>
        </div>
    );
};

export default Insta;
```
